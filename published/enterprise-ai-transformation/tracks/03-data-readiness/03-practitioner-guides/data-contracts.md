---
type: Playbook
title: Data Contracts
description: A practitioner guide to data contracts — formal, enforced agreements between data producers and consumers that prevent silent breaking changes, expressed as code.
tags: [data-contracts, data-governance, schema, data-quality, mlops]
timestamp: "2026-06-12"
---

## The Problem

Every data team has experienced this. An upstream engineer renames a column, changes a data type, or stops populating a field that was always populated. They didn't think anyone was depending on the old behavior. Nobody told them. The change ships, and three days later a model is producing wrong outputs, a pipeline is failing, or a dashboard is broken — and nobody can immediately explain why.

This is the core failure mode that data contracts solve. Not bad intentions, not incompetence — just the absence of a formal, enforced agreement between the people who produce data and the people who depend on it.

A data contract is that agreement, expressed as code. It specifies what data will be delivered, in what shape, at what quality, and with what reliability guarantees. When a producer makes a change that would break the contract, the CI/CD pipeline catches it and blocks the change before it merges. The consumer never sees it. The incident never happens.

The concept borrows directly from software engineering, where API contracts have been standard practice for years. An API contract defines what endpoints exist, what inputs they accept, and what outputs they guarantee. Data contracts apply the same discipline to datasets. As [datacontract.com](http://datacontract.com) puts it: bringing software engineering best practices into the world of data, making data products as reliable and well-defined as APIs.

---

## What a Contract Actually Contains

Most contracts are written in YAML — human-readable, machine-parseable, version-controlled alongside the pipeline code that produces the data. The Open Data Contract Standard (ODCS), maintained by the Linux Foundation's Bitol project, defines the canonical structure.

A complete contract has three layers that serve different audiences and different purposes.

**The technical layer** defines what the data looks like and how it should behave. This is what machines check automatically.

**Schema** specifies field names, data types, whether each field is required, and the allowed values for categorical fields. This is the specification consumers build against — if you join on `customer_id`, the contract guarantees it exists, it's a string, and it follows the format `CUST-XXXXXXXX`.

```yaml
fields:
  - name: customer_id
    type: string
    required: true
    description: Unique identifier. Format CUST-XXXXXXXX
  - name: account_status
    type: string
    required: true
    enum: [active, inactive, suspended, prospect]
  - name: created_at
    type: timestamp
    required: true
```

**Quality rules** are quantified, testable thresholds — not aspirational statements. The difference between "email should be valid" and "email must match a valid pattern with 99.5% compliance" is the difference between a wish and an enforceable commitment.

```yaml
quality:
  - rule: customer_id must not be null
    threshold: 100%
  - rule: email must match valid email pattern
    threshold: 99.5%
  - rule: completeness of phone_number
    threshold: 85%
```

**SLAs** define the freshness, availability, and responsiveness commitments. When will this data be updated? What percentage uptime does the producer commit to? How quickly will critical issues be acknowledged?

```yaml
sla:
  freshness: updated within 4 hours of source event
  availability: 99.5% uptime
  incident_response: critical issues acknowledged within 1 hour
```

**The human layer** is what makes the technical layer meaningful. Without it, consumers can read the schema but can't understand what it means or who to call when something breaks.

**Ownership** is a named person — not a team alias, not a distribution list. When a contract violation fires at 2am, there is one person accountable. That person's name and contact is in the contract.

**Semantics** are the business definitions. What does `customer_id` actually mean? Does it include trial accounts? Churned customers? Internal test accounts? Without explicit semantics, two consumers will interpret the same field differently and build incompatible models.

**The legal layer** defines the rules of engagement for data use.

**Terms of use** cover access restrictions, permitted use cases, compliance obligations — GDPR, CCPA, PII handling — and any restrictions on using this data for AI training. This is what prevents a dataset consented for one purpose from being quietly repurposed for model training.

---

## How Enforcement Actually Works

A contract that exists only as a document is not a contract. It is a policy statement that will be violated the moment someone is under deadline pressure and hasn't read it. Real enforcement requires three layers working together — and understanding how they work together is what separates teams that get value from contracts from teams that write contracts and then ignore them.

**Layer 1: CI/CD enforcement** is where contracts earn their keep. Every time a producer makes a code change, the pipeline validates the contract before the change is allowed to merge. A renamed field, a removed required column, a changed data type — all caught automatically, before they reach production, before any consumer is affected. This is shift-left enforcement: the cost of fixing a violation at merge time is minutes. The cost of fixing it after it's been in production for three days is days.

**Layer 2: Pipeline quality checks** run every time new data is produced. Each quality rule in the contract becomes an automated assertion. If incoming data violates a rule — null rate on a required field exceeds threshold, an invalid enum value appears — the pipeline fails and alerts the producer. Bad data does not silently reach downstream consumers. This layer catches quality degradation that schema validation alone would miss: data that has the right shape but the wrong values.

**Layer 3: Production observability** monitors SLA compliance continuously. Freshness SLAs trigger alerts if data hasn't updated within the committed window. Quality scores are tracked over time. Violations surface in the data catalog, visible to both producers and consumers. This layer catches gradual drift that individual pipeline runs might not catch — a table that's technically updating but taking longer each day to arrive, trending toward an SLA violation before it crosses the threshold.

Contracts should live in the data catalog linked to the assets they govern. A consumer researching a dataset should find the contract before they write a single line of code against it. Violations should be visible to owners in real time — not discovered by consumers when something breaks.

---

## Why AI Makes This Non-Negotiable

Data contracts matter for any data-dependent system. For AI specifically, they are not optional — because AI failure modes from contract violations are silent and delayed in a way that dashboard failures are not.

A broken dashboard surfaces immediately. Someone opens it, sees the wrong number, files a ticket. The feedback loop is hours.

A model trained on data that quietly violated a contract produces subtly wrong outputs. The model trains successfully. Evaluation metrics look fine. The wrong patterns get baked into the weights. And then for weeks or months, the model makes slightly wrong decisions — in ways that are very hard to diagnose without tracing back to the training data quality.

**Training data contracts** are the first place to start. Every dataset used for AI training should have a contract. A failing contract is a hard block on training — not a warning, not a ticket, a block. Training on bad data is not recoverable by cleaning the model after the fact.

**Feature store contracts** address a specific failure mode: training-serving skew. The same feature computed differently at training time versus serving time will cause a model that performs well in evaluation to degrade in production. A contract binding the feature engineering pipeline to both training and serving pipelines makes this structurally impossible rather than dependent on vigilance.

**Agent tool contracts** apply the same logic to agentic systems. When an agent calls a tool, it makes a data access request with implicit assumptions about what it will receive. An agent expecting a non-null `account_status` field that receives null will make a wrong decision with no obvious error to surface. Tool definitions should specify the schema, quality guarantees, and freshness of what they return.

**RAG corpus contracts** govern the documents feeding retrieval pipelines. A RAG system that retrieves stale or malformed documents generates unreliable responses — but the model doesn't know the document was stale. Contracts on the corpus define the minimum freshness and completeness required before documents are eligible for retrieval.

---

## How to Implement

The most common mistake is trying to contract everything at once. One well-enforced contract that prevents a real incident is worth more than fifty contracts that nobody maintains.

**Start with the highest-pain dataset.** Find the dataset that causes the most recurring incidents for downstream consumers — the one that breaks something two or three times a year. Every organization has one. Write the contract for that. Enforce it. When stakeholders ask why pipelines are failing fewer times, you have your business case for expanding.

**Write contracts with consumers, not for them.** The producer knows what the data is. The consumer knows what they need it to be. These are different things. A contract written by the producer alone will miss the quality guarantees consumers actually depend on. Run a joint session. The producer defines what they can reliably commit to. The consumer defines what they require. The contract is the intersection.

**Version contracts exactly like code.** Every contract lives in the same git repository as the pipeline that produces the data. Changes go through pull request review. Breaking changes require advance notice to all consumers and a documented migration period. This is not bureaucracy — it's the mechanism by which producers and consumers maintain a working relationship over time.

**Be explicit about what's breaking and what isn't.** Not all changes break contracts. Adding an optional field is non-breaking. Renaming any existing field is breaking. Changing a type is breaking. Removing a field is breaking. Changing enum values is breaking. Write this taxonomy down once, apply it consistently, and train both producers and consumers to understand it.

**Deploy in warning mode first.** When applying contracts to an existing pipeline for the first time, run quality checks in warning mode before switching to blocking. Warning mode surfaces existing violations so you can remediate them before enforcement creates new incidents. The goal of warning mode is not to stay there — it's to make the transition to blocking mode safe.

---

## Tooling

The tooling landscape for data contracts splits across the three enforcement layers. Most teams use two tools in combination: one for CI/CD and pipeline enforcement, one for production observability.

**Data Contract CLI and Editor** — the open-source reference implementation of the ODCS standard. A command-line tool and web editor for creating, validating, and testing contracts. Generates documentation automatically, supports publishing to catalogs, and runs quality tests against real data. The right starting point for teams that want a standard-based approach without vendor lock-in.
Website: [https://datacontract.com](https://datacontract.com) \| Free and open source.

**dbt contracts** — native contract enforcement built into dbt v1.5. Schema constraints and quality expectations defined directly in dbt model YAML files. Runs at compilation and pipeline execution. For teams already using dbt for transformation, this is zero new infrastructure — it's enforcement built into the tool you're already using.
Website: [https://docs.getdbt.com/docs/collaborate/govern/model-contracts](https://docs.getdbt.com/docs/collaborate/govern/model-contracts) \| Included in dbt Core and dbt Cloud.

**Soda** — SodaCL (Soda Check Language) allows quality rules to be written in YAML and run against any data warehouse. Functions as the quality check enforcement layer of a contract — the checks in the contract become Soda checks in the pipeline. More accessible to non-engineers than Great Expectations; collaborative UI for stewards who need to own rules without writing Python.
Website: [https://www.soda.io](https://www.soda.io) \| Open source core; Soda Cloud pricing on request.

**Monte Carlo** — the production observability layer. Monitors SLA compliance, freshness, volume, and schema commitments continuously in production. Complements CI/CD enforcement: CI/CD catches violations at change time, Monte Carlo catches drift and degradation in production between changes. The two tools cover different failure modes.
Website: [https://www.montecarlodata.com](https://www.montecarlodata.com) \| Enterprise pricing.

**Atlan** — if you're using Atlan as your catalog and governance layer, it provides contract management directly in the catalog. Contracts stored alongside lineage and quality signals, violations surface in the catalog, alerts route through governance workflows to named owners. Best for organizations that want a single governed platform rather than separate tools.
Website: [https://atlan.com](https://atlan.com) \| Enterprise pricing.

---

## Readiness Checklist

- [ ] Highest-pain dataset identified — the one that causes the most recurring incidents
- [ ] Contract written covering schema, quality rules, SLAs, ownership, semantics, and terms of use
- [ ] Contract stored in version control alongside the pipeline that produces the data
- [ ] Consumer input gathered before contract was finalized — not written by the producer alone
- [ ] Breaking vs. non-breaking change policy written and communicated to both producer and consumers
- [ ] CI/CD enforcement active — breaking schema changes blocked before merge
- [ ] Quality rules running as automated pipeline checks — blocking, not advisory
- [ ] Contract deployed in warning mode first, violations remediated, then switched to blocking
- [ ] Contracts linked in the catalog and discoverable by consumers before they build
- [ ] Violation alerts routing to the named owner with a defined response SLA
- [ ] All AI training datasets covered — contract failure blocks training, not just logs a warning
- [ ] Feature store contracts defined — training and serving pipelines use identical feature definitions
- [ ] Agent tool definitions include schema and quality contracts

---

## Sources

- [datacontract.com](http://datacontract.com) — The Complete Guide to Data Contract Standards, Tools & Best Practices
- Atlan — Data Contracts Explained: Key Aspects, Tools, Setup in 2026 (December 2025)
- DataHub — What Are Data Contracts? A Practical Guide (April 2026)
- Airbyte — Data Contracts: What Are They & Do You Need Them? (September 2025)
- OvalEdge — Data Contract in Data Mesh (May 2026)
- dbt Labs — Model Contracts documentation
