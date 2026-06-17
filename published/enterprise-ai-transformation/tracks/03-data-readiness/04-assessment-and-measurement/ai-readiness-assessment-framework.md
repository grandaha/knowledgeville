---
type: Playbook
title: AI Readiness Assessment Framework
description: A seven-dimension framework for assessing whether the organizational conditions for AI success exist before committing budget to building.
tags: [ai-readiness, assessment, maturity-model, data-governance, strategy]
timestamp: "2026-06-12"
---

## What This Is For

An AI readiness assessment tells you whether the organizational conditions for AI success actually exist — before you commit budget to building.

Most organizations skip the assessment. They announce an AI initiative, fund a model, discover the data isn't ready, and spend 12 months fixing foundations they could have assessed in 90 minutes. The assessment doesn't prevent that work. It sequences it correctly.

This framework produces a prioritized gap list, not a score to report upward. A score that doesn't change what gets funded next quarter is a waste of everyone's time.

> Organizations scoring above **70%** on readiness assessments are **3x more likely** to implement AI successfully within 12 months *(Deloitte, 2025)*

> Approximately **one-third** of large enterprises have begun scaling AI programs — while nearly two-thirds remain in the experimentation or piloting phase *(McKinsey State of AI, 2025)*

> Organizations investing at least **10%** of their AI budget in change management and training are **1.5x more likely** to succeed *(BCG)*

---

## The Seven Dimensions

This framework scores AI readiness across seven dimensions, each on a 1–5 scale. They score independently. The combination tells you where to invest first.

### Dimension 1: Data

The fuel of AI. Data must exist, be accessible, and be clean enough to learn from.

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

The dimension most assessments underweight and most failures trace back to. A technically excellent program fails if leadership doesn't champion it and business teams don't trust it.

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

| Level | Name | Where you are |
| --- | --- | --- |
| 1 | Nascent | AI is aspirational. No operational foundation. Pilots exist in isolation without repeatable process. |
| 2 | Developing | Some foundational elements in place. Governance is informal. Pilots succeed but don't scale. Most mid-market organizations in 2025. |
| 3 | Emerging | Working pilots, some production models. Data and governance foundations are being built. Where most enterprise AI programs sit in 2026. |
| 4 | Scaling | Production AI across multiple use cases. MLOps mature. Governance operational. AI embedded in workflows. Fewer than 25% of large enterprises. |
| 5 | Transformational | AI is a core competitive capability. Self-reinforcing data flywheel. Less than 5% of enterprises globally. |

The gap between Level 3 and Level 4 is where most programs stall. The organization has working pilots but lacks the operating model, governance infrastructure, and data architecture to scale without re-engineering each deployment from scratch.

---

## How to Run the Assessment

**Assemble the right group.** No single function can score all seven dimensions accurately. You need data, IT, business, compliance, and leadership in the room. A cross-functional session of 90–120 minutes is the minimum. Without multiple functions present, the scores will reflect one team's perspective rather than the organization's actual state.

**Score on evidence, not intent.** For each dimension, rate 1–5 and capture the evidence that supports the score. Not "we plan to implement X" but "we have X in place and can demonstrate it." The value of the assessment comes entirely from honest scoring. A score inflated by optimism produces a roadmap built on fiction.

**Plot the radar.** Map all seven scores on a radar chart. The shape tells you more than the average. A high infrastructure score with low data and governance scores means you've invested in the wrong layer. A high strategy score with low data and process scores means leadership ambition is outrunning operational readiness. The pattern is the insight.

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

**Interpreting the average:**

- 1.0–2.0: Fix data and governance before launching any AI initiative.
- 2.0–3.0: Pilot-ready but not production-ready. Identify and address the binding constraint.
- 3.0–4.0: Production-capable for specific use cases. Build systematically toward scaling.
- 4.0–5.0: Scaling-ready. Expand use case coverage and focus on continuous improvement.

---

## What to Do With the Results

The most common failure mode: the assessment produces a slide deck that gets presented to leadership and filed.

Results should drive four specific decisions:

**Budget reallocation** — if data scores 2 and infrastructure scores 4, stop buying ML tooling and fund data governance instead.

**Hiring decisions** — if talent scores 2, the next hire is not another data scientist. It is an ML engineer or applied AI practitioner in a business unit.

**Project sequencing** — AI initiatives that require capabilities you don't yet have should be sequenced after those capabilities are built, not before.

**Governance council agenda** — the lowest-scoring dimensions should be standing agenda items until they improve.

---

## Sources

- Intuz — AI Readiness Assessment 2026: 5-Dimension Enterprise Scorecard (April 2026)
- Infomineo — AI Readiness Assessment: A Practical Framework (May 2026)
- [Best-AI.org](http://Best-AI.org) — AI Readiness Framework: 7 Dimensions (February 2026)
- The Thinking Company — AI Readiness Assessment: 8-Dimension Framework (March 2026)
- McKinsey — State of AI (2025)
- Deloitte — Trusted AI Survey (2025)
- BCG — Winning with AI (2023)
