---
type: Playbook
title: AI Readiness Assessment Framework
description: A use-case-first check for whether an AI initiative needs readiness work, plus an optional seven-dimension lens for organizations planning a portfolio at once.
tags: [ai-readiness, assessment, maturity-model, use-case-scoping, strategy]
timestamp: "2026-07-03"
---

## What This Is For

[Data readiness is a use-case property](/enterprise-ai-transformation/tracks/03-data-readiness/readiness-is-a-use-case-property.md),
so the first question an assessment has to answer is which use case, on which path, at
what autonomy — not "how ready is the organization." This framework runs in two layers.
The first layer checks a single use case in minutes. The second is an optional,
heavier org-wide lens for teams planning several AI initiatives at once, not a gate every
use case has to clear.

Most organizations skip straight to funding a model, discover the data is not ready, and
spend 12 months fixing foundations they could have scoped in 90 minutes. The assessment
does not prevent that work. It sequences it correctly, and it stops teams from doing
foundation work that a low-stakes use case never needed in the first place.

This framework produces a prioritized gap list, not a score to report upward. A score that
does not change what gets funded next quarter is a waste of everyone's time.

---

## Layer 1: Check the Use Case First

Before assembling a cross-functional group for the full assessment below, place the
specific use case in front of you on two axes:

1. **Data path** — does it route around the system of record, or through it? Use [Data
   Readiness Is a Use-Case Property](/enterprise-ai-transformation/tracks/03-data-readiness/readiness-is-a-use-case-property.md).
2. **Autonomy** — does a human review every output, or does it act without review? Use
   [The Four Levels of Workflow AI
   Integration](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md).

A use case that routes around the system of record, or stays at draft-level autonomy,
rarely needs anything from Layer 2. Read the relevant [framework
pages](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/index.md) —
Data Quality, Governance, Access & Integration, Lineage & Metadata — for what that specific
path needs, and ship it. Layer 2 exists for the case that keeps coming up as autonomy and
stakes rise: several use cases at once that route through a system of record and act
without review, where the constraint is no longer any single use case's data but the
organization's shared infrastructure, governance, and talent.

---

## Layer 2: The Portfolio-Wide Seven Dimensions (Optional)

Run this layer when you are planning a portfolio of AI initiatives, most of which route
through a system of record at rising autonomy — not to score a single use case. If Layer 1
told you this is a low-stakes use case, skip to the framework pages instead; this section
will not tell you anything Layer 1 did not already answer.

> Only **13%** of organizations are fully ready to deploy and use AI — readiness, not ambition, is the constraint ([Cisco, 2024](#ev-cisco-ai-readiness-2024-fully-ready))

> Approximately **one-third** of organizations have begun scaling AI across the enterprise.
> Larger companies lead; the rest have not yet reached the scaling phase ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-scaling-by-size))

> BCG's **10-20-70** rule: AI success comes 10% from algorithms, 20% from technology and data, and **70% from people and process** ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy))

---

## The Seven Dimensions

This layer scores organization-wide AI readiness across seven dimensions, each on a 1–5
scale. They score independently. The combination tells you where the organization should
invest first for its *portfolio* of AI work — it is not a per-use-case gate.

### Dimension 1: Data

A model learns only from the data it can reach, so data must exist, be accessible, and be clean enough to learn from.

| Level | What it looks like |
| --- | --- |
| 1 | Data siloed across systems. No quality standards. No catalog. No governance. |
| 2 | Some consolidation in a warehouse or lake. Basic quality awareness. Catalog absent or stale. |
| 3 | Unified data platform. Quality checks exist but are manual or intermittent. Catalog partially populated. |
| 4 | Active metadata and continuous quality monitoring. Contracts on AI-critical datasets. Catalog current. |
| 5 | Full governance operationalized. All AI training data has contracts, lineage, and continuous quality gates. Real-time pipelines available for agentic use cases. |

Evidence to collect: catalog coverage percentage, quality scores for AI-critical assets, percentage of datasets with active contracts, data incident rate and MTTR.

### Dimension 2: Data Governance

Governance determines whether AI initiatives are trustworthy, compliant, and auditable.

| Level | What it looks like |
| --- | --- |
| 1 | No data ownership. No policies. No governance council. |
| 2 | Informal ownership. Ad hoc policies. No enforcement mechanism. |
| 3 | Named data owners per domain. Policies documented. Limited automated enforcement. |
| 4 | Governance council active. Policy-as-code in CI/CD. Bias testing gates before model deployment. |
| 5 | Full AI governance lifecycle. Model cards for all production models. EU AI Act tiers assessed. Compliance monitoring automated. |

Evidence to collect: percentage of AI-critical assets with named owners, policy enforcement automation rate, regulatory tier assessments completed.

### Dimension 3: Infrastructure

Whether AI workloads can run at production scale reliably.

| Level | What it looks like |
| --- | --- |
| 1 | No ML infrastructure. Models on analyst laptops. No versioning, monitoring, or reproducibility. |
| 2 | Cloud compute available. Some managed ML tooling. No CI/CD for models. |
| 3 | Managed ML platform (SageMaker, Vertex, Databricks). Basic model registry. Experiment tracking in place. |
| 4 | Full MLOps: CI/CD for models, feature store, drift monitoring, automated retraining. |
| 5 | LLMOps and AgentOps for generative and agentic workloads. Semantic logging, prompt versioning, agent trace trees. Token cost monitoring active. |

Evidence to collect: MLOps maturity level, model registry coverage, mean time to detect model drift, LLMOps tooling presence.

### Dimension 4: Talent and Skills

The most common gap is not at the top (data scientists) but in the middle — applied practitioners who translate between business problems and technical solutions.

| Level | What it looks like |
| --- | --- |
| 1 | No AI/ML skills. Fully dependent on external vendors. |
| 2 | One or two data scientists. No ML engineers. No AI literacy in business teams. |
| 3 | ML engineering capability. Some business team AI literacy. Training programs just starting. |
| 4 | Full data science and ML engineering. Applied AI-literate practitioners in business units. Structured literacy training. |
| 5 | AI embedded across business roles. Teams identify opportunities, interpret outputs, and challenge models. Continuous learning culture. |

Evidence to collect: ratio of ML engineers to data scientists, AI literacy training completion rates, percentage of business roles with AI competency requirements.

### Dimension 5: Process Maturity

AI can only improve processes that are understood, documented, and measurable.

| Level | What it looks like |
| --- | --- |
| 1 | Processes tribal and undocumented. No measurement baseline. |
| 2 | Key processes documented informally. Some KPIs tracked. |
| 3 | Core processes documented with defined inputs, outputs, and owners. Basic AI use cases identified. |
| 4 | Processes actively measured and managed. AI opportunities mapped to specific improvement targets. |
| 5 | Continuous improvement culture. AI integrated into process workflows. Outcomes tracked against AI-driven targets. |

Evidence to collect: percentage of AI-targeted processes with documented baselines, pilot-to-production conversion rate.

### Dimension 6: AI Risk and Compliance

AI-specific risk management: model risk, regulatory compliance, ethical AI. Separate from data governance.

| Level | What it looks like |
| --- | --- |
| 1 | No AI risk management. No awareness of applicable regulations. |
| 2 | Basic GDPR/data privacy awareness. No AI-specific risk framework. |
| 3 | NIST AI RMF or equivalent framework identified. Some bias testing. EU AI Act tiers assessed for deployed systems. |
| 4 | Formal AI risk program. Bias gates before deployment. Model cards for all production models. Incident response plan tested. |
| 5 | Continuous AI risk monitoring. Regulatory change tracking automated. Third-party vendor security assessments complete. |

Evidence to collect: NIST AI RMF adoption status, EU AI Act tier assessments, bias testing gate compliance, model card coverage.

### Dimension 7: Strategy and Culture

The dimension most assessments underweight and most failures trace back to. A technically excellent program fails if leadership does not champion it and business teams do not trust it.

| Level | What it looks like |
| --- | --- |
| 1 | No AI strategy. AI treated as an IT project. No executive sponsor. |
| 2 | AI strategy exists on paper. No clear business outcome targets. Minimal executive visibility. |
| 3 | Strategy tied to specific business objectives. Executive sponsor identified. Some cross-functional alignment. |
| 4 | Strategy operationalized with funded roadmap, business outcome KPIs, and cross-functional governance. |
| 5 | AI embedded in corporate strategy. Leadership champions data-driven culture. AI ROI reported at board level. Change management is a funded line item. |

Evidence to collect: written AI strategy with outcome targets, executive sponsor with P&L accountability, change management budget allocation.

---

## The Five Maturity Levels

These five levels describe the organization's overall AI maturity, not any single use
case's readiness. A Level 2 organization can still ship a use case that routes around the
system of record and stays at draft-level autonomy — the organization's maturity score
does not gate that use case.

| Level | Name | Where you are |
| --- | --- | --- |
| 1 | Nascent | AI is aspirational. No operational foundation. Pilots exist in isolation without repeatable process. |
| 2 | Developing | Some foundational elements in place. Governance is informal. Pilots succeed but do not scale. Most mid-market organizations in 2025. |
| 3 | Emerging | Working pilots, some production models. Data and governance foundations are being built. Where most enterprise AI programs sit in 2026. |
| 4 | Scaling | Production AI across multiple use cases. MLOps mature. Governance operational. AI embedded in workflows. Fewer than 25% of large enterprises. |
| 5 | Transformational | AI is a core competitive capability. Self-reinforcing data flywheel. Less than 5% of enterprises globally. |

The gap between Level 3 and Level 4 is where most programs stall. The organization has working pilots but lacks the operating model, governance infrastructure, and data architecture to scale without re-engineering each deployment from scratch.

---

## How to Run the Assessment

Run this once Layer 1 has confirmed the portfolio genuinely needs the org-wide view — a
mix of through-the-system-of-record use cases rising toward autonomous action, not a
single low-stakes one.

**Assemble the right group.** No single function can score all seven dimensions accurately. You need data, IT, business, compliance, and leadership in the room. A cross-functional session of 90–120 minutes is the minimum. Without multiple functions present, the scores will reflect one team's perspective rather than the organization's actual state.

**Score on evidence, not intent.** For each dimension, rate 1–5 and capture the evidence that supports the score. Not "we plan to implement X" but "we have X in place and can demonstrate it." The value of the assessment comes entirely from honest scoring. A score inflated by optimism produces a roadmap built on fiction.

**Plot the radar.** Map all seven scores on a radar chart. The shape shows more than the
average does. A high infrastructure score with low data and governance scores means the
organization has invested in the wrong layer. A high strategy score with low data and
process scores means leadership ambition is outrunning operational readiness.

**Identify the binding constraint.** One dimension is almost always the limiting factor — the one that caps AI progress regardless of strength elsewhere. A Level 5 infrastructure with a Level 1 data foundation cannot produce reliable AI. The binding constraint is what to fix first, before anything else. Adding capability on top of a binding constraint produces waste, not progress.

**Define 90-day actions, not a multi-year roadmap.** For the lowest-scoring dimensions, define concrete, owned, measurable actions that can be completed in the next quarter. The assessment is only valuable if it changes what gets funded and prioritized in the next 90 days. A multi-year roadmap produced from this assessment without a 90-day commitment is a plan to plan.

---

## Scoring Template

Use this in your assessment session:

| Dimension | Score (1–5) | Supporting evidence | Key gap | 90-day action |
| --- | --- | --- | --- | --- |
| Data |  |  |  |  |
| Data Governance |  |  |  |  |
| Infrastructure |  |  |  |  |
| Talent & Skills |  |  |  |  |
| Process Maturity |  |  |  |  |
| AI Risk & Compliance |  |  |  |  |
| Strategy & Culture |  |  |  |  |
| **Average** |  |  |  |  |

**Interpreting the average:** this is a portfolio signal, not a per-use-case gate. Match it
to the use case's Layer 1 placement rather than reading it as a blanket stop-light.

A use case that routes around the system of record or stays at draft-level autonomy is
never gated by this score — ship those at any organizational maturity level. The bands
below describe only through-the-record use cases at rising autonomy, the category this
score actually governs.

- 1.0–2.0: The organization-wide foundation is weak. Fix the binding constraint before
  committing to a through-the-record program that acts on autonomy.
- 2.0–3.0: Pilot-ready, not production-ready. Identify and address the binding constraint
  before scaling.
- 3.0–4.0: Production-capable for specific through-the-record use cases. Build
  systematically toward scaling the portfolio.
- 4.0–5.0: Scaling-ready across the portfolio, including higher-autonomy, through-the-record
  use cases. Expand coverage and focus on continuous improvement.

---

## What to Do With the Results

The most common failure mode: the assessment produces a slide deck that gets presented to leadership and filed.

Results should drive four specific decisions:

**Budget reallocation** — if data scores 2 and infrastructure scores 4, stop buying ML tooling and fund data governance instead.

**Hiring decisions** — if talent scores 2, the next hire is not another data scientist. It is an ML engineer or applied AI practitioner in a business unit.

**Project sequencing** — AI initiatives that require capabilities you do not yet have should be sequenced after those capabilities are built, not before.

**Governance council agenda** — the lowest-scoring dimensions should be standing agenda items until they improve.

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Cisco — *Cisco 2024 AI Readiness Index*, 2024.** Only 13% of companies today are fully ready to capture AI's potential — down from 14% a year ago. [View source](https://newsroom.cisco.com/c/r/newsroom/en/us/a/y2024/m11/cisco-2024-ai-readiness-index-urgency-rises-readiness-falls.html){#ev-cisco-ai-readiness-2024-fully-ready} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI in 2025*, 2025.** About one-third of organizations have begun to scale AI across the enterprise; larger companies are the most likely to have reached the scaling phase. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-scaling-by-size} · verified 2026-06-20 · primary
- **BCG — *Where's the Value in AI?*, 2024.** AI leaders follow the rule of putting 10% of their resources into algorithms, 20% into technology and data, and 70% into people and processes. [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-2024-ten-twenty-seventy} · verified 2026-06-20 · primary
