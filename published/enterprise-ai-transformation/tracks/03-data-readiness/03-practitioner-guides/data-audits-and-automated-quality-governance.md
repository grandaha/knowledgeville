---
type: Playbook
title: Data Audits & Automated Quality Governance
description: A practitioner guide to conducting data audits and automating continuous quality governance so data quality becomes an operational property of the infrastructure.
tags: [data-quality, governance, data-audit, observability, mlops]
timestamp: "2026-06-12"
---

## What This Document Covers

Knowing that data quality matters is not the same as knowing how to measure it, enforce it, and sustain it. This is a practitioner guide covering:

1. How to actually conduct a data audit for accuracy and completeness
2. How to translate audit findings into measurable, enforced quality rules
3. How to automate those rules so governance runs continuously
4. How to connect automation to remediation so issues get fixed, not just flagged

The goal: data quality that is not a project that runs once and decays, but an operational property of the infrastructure enforced automatically, visible continuously, and owned by named people.

---

## Part 1: How to Conduct a Data Audit

### What a Data Quality Audit Actually Is

A data quality audit is a systematic review of data assets to determine whether they meet defined standards for accuracy, completeness, consistency, validity, and timeliness. It runs in two modes:

- Internal continuous auditing — automated checks running on a schedule or triggered by pipeline events
- External periodic auditing — independent review of quality practices and compliance posture, typically annually or before a major AI initiative

For AI readiness specifically, audits serve a third purpose: fitness-for-purpose validation — not just "is this data correct" but "is this data trustworthy enough to train a model or feed an agent that will act on it autonomously."

---

### Step 1: Define Scope and Objectives

Before touching any data, define exactly what you are auditing and why.

- Which systems, tables, and fields are in scope?
- What use case does this data support? Reporting? ML training? Agent decision-making?
- Which quality dimensions matter most for this use case?
- What is the acceptable quality threshold — and what happens when it is not met?
- Who is the data owner who will receive and act on findings?

Practical guidance: start with data flowing into your most critical AI systems or business decisions. Auditing everything at once produces a backlog no team can clear. Prioritize by business impact and AI risk.

---

### Step 2: Data Profiling — the Diagnostic Layer

Data profiling is automated analysis of a dataset to understand its structure, content, and statistical properties before applying any rules. It answers: what does this data actually look like?

What profiling produces:

- Row count — volume; detect unexpected drops or spikes
- Null rate per column — completeness baseline per field
- Distinct value count — cardinality; detect unexpected proliferation
- Min / max / mean / stddev — distribution; detect outliers
- Value frequency distribution — most common values; detect encoding issues
- Data type confirmation — actual types vs. declared schema
- Pattern analysis — formats present (date formats, phone formats)
- Duplicate record rate — uniqueness baseline

What to look for immediately:

- Null rates above 5% on fields declared as required  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Sentinel values (-1, 0, 9999, "N/A", "Unknown") suggesting missing data encoded as values
- Date fields with values in 1900 or 2099 — common default handling artifacts in legacy systems
- Fields where 80%+ of values are a single value — may indicate a broken pipeline defaulting to a constant  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Schema mismatches between the data dictionary and what the profiler finds

---

### Step 3: Auditing for Accuracy

Accuracy is the hardest dimension to audit at scale because it requires a reference to compare against. You need to know what the correct value should be to determine whether the value present is wrong.

Four accuracy audit techniques:

**Technique 1: Source system comparison**

Compare values in the audited dataset against the authoritative source system. Pull a statistically valid sample — at least 5% of records, or 500 records minimum. If failures cluster in a time range or system segment, expand the sample in that area.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

**Technique 2: Validation rules**

Apply domain knowledge as testable rules:

- Email addresses must match a valid regex pattern
- Transaction amounts must be greater than zero
- Order dates must be on or before ship dates
- Country codes must exist in the ISO 3166-1 standard list
- Customer status must be one of a defined controlled vocabulary

Rules applied in bulk across an entire dataset are the foundation of automated accuracy checking.

**Technique 3: Cross-system consistency check**

If the same entity exists in multiple systems, compare corresponding fields. A customer's address in the CRM should match their address in the billing system. Discrepancies identify either data entry errors or transformation bugs. For AI specifically, this detects fields that look accurate in isolation but are inconsistent across the join that forms a training dataset.

**Technique 4: Statistical anomaly detection**

For numerical data, flag values that deviate significantly from historical distributions. If average order value has been around \$150 for 12 months and a segment suddenly shows \$15,000, that is either a real business event or a data error. Z-score analysis and statistical process control automate this detection.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

Accuracy scoring:

```javascript
Accuracy Score = (Records passing all accuracy rules / Total records audited) x 100
```

Target for AI training data: 95% or above. Below 90%: block from production AI use pending remediation.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

---

### Step 4: Auditing for Completeness

Completeness is more nuanced than null rate. A field can be populated with a value that represents missing — which a null check will not catch.

**Technique 1: Null rate analysis by field**

For each field, calculate the percentage of records where the value is null or empty. Compare against acceptable thresholds:

- Primary key: 0% nulls acceptable  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Required business fields (email, account ID): under 1%  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Optional enrichment fields: document the rate; context-dependent threshold

**Technique 2: Sentinel value detection**

Build a sentinel value register for your environment. Common sentinel values:

- Numeric: -1, 0, 999, 9999, -999
- String: "N/A", "Unknown", "None", "TBD", "NULL" as a string
- Date: 1900-01-01, 2099-12-31, 1970-01-01 (Unix epoch default)

Treat sentinel values as nulls in completeness scoring. A field that is 98% complete by null count but 25% sentinel-value is actually 73% complete.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

**Technique 3: Conditional completeness**

Completeness rules that apply when another condition is true:

- If order status is "shipped" then ship date must not be null
- If customer type is "enterprise" then contract value must not be null

Flat null rate analysis misses these. Conditional completeness requires SQL-based or code-based assertion logic.

**Technique 4: Cross-record completeness**

For time-series data, check whether expected records exist. If you expect a transaction record for every active customer every month, and 3% of active customers have no record in March, that is a completeness failure at the record level — not the field level.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

Completeness scoring:

```javascript
Completeness Score = (Required fields populated with valid values /
                      Required fields x Total records) x 100
```

Target for AI training data: 98% or above for primary fields. Below 95%: flag for steward review.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

---

### Step 5: Document Findings

For each finding document:

- Asset — which table, field, or pipeline
- Dimension — which quality dimension failed
- Severity — critical (blocks AI use), major (degrades AI quality), minor (cosmetic)
- Scope — what percentage of records are affected
- Root cause hypothesis — where in the pipeline did this likely originate
- Owner — named data steward accountable for remediation
- Recommended action — specific fix, not a general suggestion
- AI impact — which models, features, or agents are downstream of this issue

---

## Part 2: Automating Data Quality Governance

### Why Manual Audits Do Not Scale

A manual audit conducted quarterly means 87 days of undetected data quality degradation between each check. At AI scale — where agents make decisions continuously based on pipelines that run 24/7 — manual quality processes are not a governance strategy. They are compliance theater that provides the appearance of oversight without the substance.

Automated data quality governance shifts the manual work from running checks to designing checks and resolving issues — the two activities that require human judgment.

---

### The Automation Architecture: Four Layers

Layer 1 — PROFILING AND DISCOVERY
Schema, statistics, lineage, catalog. Runs automatically on schedule. Produces continuously updated profiles for every monitored asset.

Layer 2 — TESTING AND VALIDATION
Rules as code, CI/CD gates, pipeline checks. Quality rules version-controlled and enforced automatically. Failing rules block the pipeline — they do not produce warnings that get ignored.

Layer 3 — OBSERVABILITY AND ALERTING
Drift detection, anomaly alerts, dashboards. ML-powered detection catches failure modes that static rules don't anticipate.

Layer 4 — GOVERNANCE AND REMEDIATION
Routing, ownership, SLAs, resolution tracking. Issues automatically routed to named owners with context, SLA clock started, resolution tracked in governance reporting.

Most organizations have Layer 1. Production-grade AI governance requires all four.

---

### Layer 2: Testing and Validation in Practice

The shift-left principle: quality checks run as early in the pipeline as possible. A check at ingestion catches an issue before it propagates to 47 downstream tables and 3 production models.

Rule categories:

Schema rules (dbt):

```javascript
not_null:
  - customer_id
  - order_date
  - email
```

Range and validity rules (Great Expectations):

```javascript
expect_column_values_to_be_between(
    column="transaction_amount",
    min_value=0.01, max_value=1000000
)
expect_column_values_to_match_regex(
    column="email",
    regex="[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}"
)
```

Conditional completeness (Soda):

```javascript
checks for orders:
  - missing_count(ship_date) = 0:
      filter: status = 'shipped'
  - missing_count(contract_value) = 0:
      filter: customer_type = 'enterprise'
```

Cross-table consistency (dbt custom test):

```javascript
SELECT COUNT(*) FROM orders
WHERE ship_date < order_date
-- Expected result: 0
```

CI/CD integration: quality tests run before any code change is merged. A PR that introduces a schema change breaking a downstream quality rule is rejected automatically before it reaches production.

---

### Layer 3: ML-Powered Observability

Static rules catch known failure modes. Observability catches unknown ones. ML-powered platforms learn the normal behavior of a data asset and alert when something changes unexpectedly — without requiring a human to have written a rule for every possible failure mode.

What observability monitors:

- Volume — row count drops or spikes outside normal range
- Freshness — tables not updated within their expected window
- Schema drift — columns added, dropped, or type-changed without a code change
- Distribution shift — field value distributions diverging from historical baseline
- Null rate change — completeness degrading over time
- Duplicate rate change — sudden increase in duplicate records

How ML-powered detection works (Monte Carlo model):

1. Platform reads metadata and statistical signals from connected warehouses via read-only connectors
2. ML establishes behavioral baselines per asset per metric
3. Anomalies flagged when current values deviate beyond learned thresholds
4. Root cause analysis traces the anomaly upstream through lineage
5. Alert routed to the asset owner with downstream impact shown

Alert design principles:

- Route to named owners, not generic Slack channels
- Include downstream impact in the alert — which models, dashboards, agents are affected
- Classify severity automatically
- Suppress known false positives (expected volume drops on weekends)
- Track MTTD and MTTR as governance KPIs

---

### Layer 4: The Automated Remediation Workflow

Detection without remediation is a dashboard that makes people feel bad. The automation loop is only closed when quality issues route to the right person, with context, and with a defined SLA.

Workflow:

1. Quality check fails or anomaly detected
2. Severity classified: critical, major, minor
3. Owner identified via catalog ownership metadata
4. Ticket created with: asset name, rule failed, % records affected, downstream AI and BI impact, root cause hypothesis
5. SLA clock starts: critical 4 hours, major 24 hours, minor 72 hours
6. Owner investigates and applies fix: pipeline bug, source system error, or rule calibration
7. Quality check re-run to confirm resolution
8. Resolution logged in catalog quality history
9. SLA compliance tracked in governance reporting

Escalation policy:

- SLA breached: escalate to steward's manager and flag in governance dashboard
- Critical issue affecting live AI: trigger inference pause for affected pipeline pending resolution
- Recurring pattern: trigger root cause review, not just symptom fix

---

### Governance Metrics to Track

- Quality score by asset: weighted composite across all dimensions — target 85% or above for AI-eligible assets  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Accuracy rate: percentage of records passing all accuracy rules — target 95% or above  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Completeness rate: percentage of required fields populated with valid values — target 98% or above  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Rule coverage: percentage of AI-critical assets with automated checks — target 100%  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- MTTD: mean time from issue introduction to detection — target under 1 hour for critical assets
- MTTR: mean time from detection to resolution — target under 4 hours critical, under 24 hours major
- SLA compliance: percentage of issues resolved within SLA — target 95% or above  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->
- Recurring issue rate: percentage of issues that recur within 30 days — target under 10%  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

---

## Part 3: Tooling Stack

No single tool covers all four layers. Most production environments use two to three working together. Here is what each tool actually is, what it does, and where to find it.

---

### Layer 2 — Testing and Validation Tools

**dbt (data build tool)**

What it is: an open-source transformation framework that lets data teams write SQL-based transformations as version-controlled code. dbt tests are assertions written alongside transformation models — they run automatically every time a transformation runs, validating that outputs meet expectations before downstream systems consume them.

Best for: teams already using dbt for transformation. Zero new infrastructure required.

Limitation: only covers dbt models; no monitoring of production data outside the transformation layer.

Website: [https://www.getdbt.com](https://www.getdbt.com)

Open source core. dbt Cloud (managed) starts at \$50/month per developer seat.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

---

**Great Expectations**

What it is: an open-source Python library for defining, documenting, and validating data quality expectations as code. You write "expectations" — assertions about what your data should look like — and run them against any dataset at any pipeline stage. Expectations are version-controlled, shareable, and runnable in CI/CD pipelines.

Best for: engineering-heavy teams that need highly customizable, code-driven validation integrated into ingestion and CI/CD workflows.

Limitation: requires Python expertise to configure; steeper learning curve than YAML-based tools.

Website: [https://greatexpectations.io](https://greatexpectations.io)

Fully open source. GX Cloud (managed UI and scheduling) is available with pricing on request.

---

**Soda**

What it is: a data quality platform that lets teams write quality checks in a simple YAML-based syntax (SodaCL) and run them against cloud warehouses. More accessible to non-engineers than Great Expectations while still supporting complex business logic. Includes a UI for collaborative monitoring and a CLI for pipeline integration.

Best for: teams that want a balance between technical flexibility and business-user accessibility. Strong for organizations where data stewards, not just engineers, need to own quality rules.

Website: [https://www.soda.io](https://www.soda.io)

Open source core (Soda Core). Soda Cloud (managed) pricing on request.

---

### Layer 3 — Observability and Monitoring Tools

**Monte Carlo**

What it is: an enterprise data observability platform that uses machine learning to automatically detect anomalies in data freshness, volume, schema, and distribution — without requiring manual rule configuration for every scenario. It connects to your data warehouse and BI tools via read-only metadata connectors, learns normal behavior for each asset, and alerts when something deviates. Root cause analysis traces anomalies back through lineage to the likely source pipeline.

Best for: large enterprises with complex multi-system data environments where manual rule coverage is impossible. The gold standard for production data observability at scale.

Limitation: enterprise pricing; best value at scale.

Website: [https://www.montecarlodata.com](https://www.montecarlodata.com)

Enterprise pricing, contact for quote.

---

**Metaplane**

What it is: a lightweight data observability platform designed for teams using dbt, Snowflake, and Looker. Automatically detects anomalies in metrics, schema, and data volume, and alerts teams before bad data reaches dashboards or models. Faster to deploy than Monte Carlo with a more accessible price point.

Best for: mid-market teams on a modern dbt-centric stack who need production observability without enterprise-scale complexity.

Website: [https://www.metaplane.dev](https://www.metaplane.dev)

Starts at approximately \$500/month.  <!-- noev: recommended threshold / target / worked example / tool pricing, not a sourced statistic -->

---

**Bigeye**

What it is: a data observability platform combining rule-based checks with ML-powered anomaly detection. Deep native integration with Snowflake and BigQuery. Monitors table freshness, volume, distribution, and schema drift. Includes column-level health scores and automatic threshold tuning.

Best for: teams primarily on Snowflake or BigQuery who want a combination of defined rules and automatic ML detection without choosing between the two approaches.

Website: [https://www.bigeye.com](https://www.bigeye.com)

Pricing on request.

---

### Layers 1 and 4 — Catalog and Governance Platforms

**Atlan**

What it is: an active metadata platform that unifies data catalog, data quality governance, lineage, and discovery in a single control plane. Atlan's Data Quality Studio lets teams define and automate quality rules directly in cloud warehouses, with trust signals and alerts embedded in everyday workflows. It integrates upstream tools like Monte Carlo, Soda, and Anomalo to provide a 360-degree quality view. For AI specifically, it serves as the context layer that agents can query programmatically to understand data assets before consuming them.

Best for: organizations that want to replace fragmented point tools with a single governed platform. Gartner Magic Quadrant Leader for Data and Analytics Governance Platforms (2026) and Metadata Management Solutions (2025).

Website: [https://atlan.com](https://atlan.com)

Enterprise pricing, contact for quote.

---

**OvalEdge**

What it is: an integrated data governance platform covering catalog, lineage, data quality rules, and business glossary management in one product. Applies business and technical rules to ensure data meets defined expectations. Continuously analyzes datasets to surface unexpected changes in structure or completeness. Recognized as a Niche Player in the 2026 Gartner Magic Quadrant for Data and Analytics Governance Platforms.

Best for: enterprises seeking a single governed platform for cataloging, lineage, and quality management at a lower price point than Atlan.

Website: [https://www.ovaledge.com](https://www.ovaledge.com)

Pricing on request.

---

### Recommended Stack by Team Size

Smaller teams and earlier-stage programs:

- Start with dbt tests plus Great Expectations for Layer 2 (both open source, zero cost to start)
- Add Soda or Metaplane for Layer 3 observability
- Use your existing catalog or a manual Notion-based tracker for Layer 4 until volume justifies a dedicated governance platform

Mid-market teams:

- dbt tests plus Soda for Layer 2
- Metaplane or Bigeye for Layer 3
- OvalEdge for Layers 1 and 4

Enterprise:

- dbt tests plus Great Expectations for Layer 2
- Monte Carlo for Layer 3
- Atlan for Layers 1 and 4

---

## Part 4: Implementation Sequence

- Weeks 1-2: Profile and baseline — run profiling on all AI-critical datasets, document null rates, distributions, sentinel values. Do not write rules yet.
- Weeks 3-4: Define quality standards — for each asset, define acceptable thresholds per dimension. Get sign-off from data owners. Document in catalog.
- Weeks 5-6: Write and deploy Layer 2 rules — start with highest-impact assets. Deploy in warning mode first to calibrate thresholds before switching to blocking.
- Weeks 7-8: Switch to blocking mode and deploy observability — rules now block pipelines. Deploy observability tooling. Tune anomaly detection.
- Weeks 9-10: Deploy governance workflows — connect alerts to ownership metadata, configure issue routing, stand up governance dashboard. Run a fire drill.
- Ongoing: Expand coverage, calibrate false positive rates, review recurring issues monthly for root cause patterns.

---

## Readiness Checklist

- [ ] All AI-critical assets profiled — null rates, distributions, sentinel values documented
- [ ] Quality thresholds defined and signed off by data owners
- [ ] Accuracy rules written as code for all required fields
- [ ] Completeness rules include sentinel value detection, not just null checks
- [ ] Conditional completeness rules defined for context-dependent fields
- [ ] All rules integrated into CI/CD pipeline — blocking, not advisory
- [ ] Shift-left applied — checks at ingestion, not only at consumption
- [ ] ML-powered observability deployed for production AI-critical assets
- [ ] Alert routing connected to catalog ownership metadata
- [ ] SLAs defined by severity
- [ ] Governance dashboard live — quality scores, issue queue, SLA compliance visible
- [ ] MTTD and MTTR tracked as operational KPIs
- [ ] Quality scores tied to AI eligibility — assets below threshold blocked from training pipeline
- [ ] Full detection-to-resolution loop tested end-to-end

---

## Sources

- Atlan — Data Quality Audit: How To Get It Right (May 2025)
- Atlan — Automated Data Quality: Fix Bad Data and Get AI-Ready (May 2025)
- Atlan — Best Data Quality Tools for 2026 (March 2026)
- OvalEdge — Data Quality Assessment: A 2026 Guide to AI-Ready Trusted Data (May 2026)
- OvalEdge — Which Data Quality Monitoring Tool Is Right for You (June 2026)
- Improvado — Data Quality Audit: The Complete Guide (April 2026)
- LatentView — What Is Data Audit? (January 2026)
- Airbyte — 4 Best Tools to Automate Data Quality Checks in ETL Pipelines (September 2025)
- DataKitchen — The 2026 Open-Source Data Quality and Data Observability Landscape (October 2025)
- Lumenalta — Data Quality Checklist (January 2026)
