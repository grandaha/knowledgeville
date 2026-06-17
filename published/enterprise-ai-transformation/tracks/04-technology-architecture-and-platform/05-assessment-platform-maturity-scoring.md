---
type: Playbook
title: "Assessment: Platform Maturity Scoring"
description: A five-dimension diagnostic for scoring AI platform maturity — API governance, tooling consolidation, developer enablement, observability, and build vs. buy discipline.
tags: [ai-platform, assessment, maturity, api-governance, mlops]
timestamp: "2026-06-17"
---

## What This Is For

This assessment scores one thing: whether the **AI platform function** is mature enough to support the AI the organization has already deployed — or is actively building. It is not a model governance audit (that is [the Track 02 governance maturity scoring](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/05-assessment-governance-maturity-scoring.md)) and it is not a data readiness audit (that is Track 03). This one measures whether the shared infrastructure layer — the API gateway, the shared embedding services, the model registry, the observability tooling, the vendor discipline — is real and operational, versus fragmented and invisible.

It is the diagnostic companion to the [AI technology architecture framework](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md) and the [practitioner guide for designing an AI platform function](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/04-practitioner-guide-designing-an-ai-platform-function.md). Run it before investing in net-new AI capabilities, when platform costs are growing without explanation, or when the number of teams building AI independently has outpaced any shared infrastructure serving them.

> Only **17% of enterprises report having centralized visibility into AI API spending across teams** — the majority cannot tell you what they spent on model APIs last month or which business unit spent it *(McKinsey & Company, 2025)*
>
> The average large enterprise runs **more than 40 distinct AI or ML tools** across business units, most of them procured independently with no shared infrastructure layer connecting them *(Databricks, 2024)*

This framework produces a prioritized gap list, not a score to report upward. If the result doesn't change what gets funded, what gets consolidated, or what gets enforced in the next 90 days, the assessment wasn't worth running.

---

## The Five Dimensions

Score each dimension on a 1–5 scale, independently, on evidence rather than intent. The dimensions don't average into a grade so much as combine into a shape — and the shape tells you where to invest first.

### Dimension 1: API Governance and Cost Visibility

This dimension measures whether the organization has centralized control over how AI APIs are accessed and whether it can account for what it spends. The question is not whether the organization has model API access — virtually all do — but whether that access is governed. Can you name what you spent on model APIs last month? Can you attribute that spend to a team or use case? Are budget limits and anomaly alerts in place? Without answers to these questions, every other platform investment is building on an invisible cost structure that can grow without warning.

| Level | What it looks like |
| --- | --- |
| 1 | No centralized API access. Teams call model providers directly with individual API keys; no cost visibility exists anywhere in the organization. |
| 2 | A shared API key or billing account exists, but usage is not attributed to teams or use cases; cost tracking is done manually post-hoc, if at all. |
| 3 | A centralized gateway exists; cost attribution by team is available in dashboards; rate limits are set; but alerts and budget controls are not automated. |
| 4 | A centralized API gateway with automated cost alerts, per-team budgets, rate limiting, and full audit logging is in operation; spend reports are generated on a defined cadence and reviewed. |
| 5 | API governance is fully automated; cost anomalies trigger alerts and auto-suspend; usage reports inform build vs. buy decisions; the gateway enforces data handling policies and approved-model restrictions. |

Evidence to collect: gateway configuration showing centralized routing, cost dashboard with per-team attribution, budget alert configuration, API audit log sample, evidence of a cost anomaly being caught and acted on.

---

### Dimension 2: Model Registry and Selection Discipline

This dimension assesses whether the organization knows which AI models it is using, why it chose them, and what it would take to replace or retire them. Ungoverned model selection produces three predictable problems: redundant spend on overlapping model capabilities, compliance exposure when models with different data-use terms are used interchangeably, and operational fragility when a vendor changes a model and no one knew which systems depended on it. A model registry is the foundational artifact that makes model decisions traceable.

| Level | What it looks like |
| --- | --- |
| 1 | No model registry. Teams choose models ad hoc; no record of what is in use or why; no compliance classification exists. |
| 2 | An informal list exists (a shared doc or wiki page) but is not maintained; new models are added without formal evaluation; compliance classification is absent. |
| 3 | A formal model registry exists with entries for each approved model, including use-case classification, cost tier, and a named owner; a basic evaluation process exists but is inconsistently applied. |
| 4 | All models in use are registered; each entry includes capability benchmarks on internal test cases, compliance classification, cost comparison, and vendor risk notes; evaluation is required before a new model is added. |
| 5 | The model registry is integrated with governance (feeds the model inventory in Track 02), is updated automatically when vendor models change, and drives developer tooling defaults; model sunset and replacement processes are defined. |

Evidence to collect: model registry document or system with dated entries, evaluation artifacts for at least one approved model, compliance classification record, process document for adding a new model, evidence of a model being removed or replaced with documentation.

---

### Dimension 3: Shared Infrastructure and Tooling Consolidation

This dimension measures whether the organization has built shared, reusable infrastructure that new AI projects can build on — or whether each team is re-solving the same infrastructure problems independently. Uncoordinated team-by-team builds produce redundant embedding pipelines, incompatible vector stores, and engineering capacity burned on infrastructure that could be shared. The platform function's primary value proposition is eliminating that duplication; this dimension scores whether it has actually done so.

| Level | What it looks like |
| --- | --- |
| 1 | No shared infrastructure. Each team builds their own embedding pipelines, vector stores, and orchestration; the organization is paying for the same problems to be solved multiple times in parallel. |
| 2 | Some shared infrastructure exists informally — a shared embedding service used by a few teams — but it is not officially supported, has no SLA, and new teams are not directed to use it. |
| 3 | Core shared infrastructure is in place (API gateway, embedding service, vector store) with defined SLAs; at least some teams are using it; reference architecture exists but is not consistently followed. |
| 4 | All new AI projects use shared infrastructure by default; reference architecture is actively maintained; teams fork from approved patterns rather than starting from scratch; a platform team is accountable for shared infrastructure health. |
| 5 | Shared infrastructure covers the full platform layer (gateway, embeddings, vector store, orchestration templates, prompt caching); platform decisions are driven by use-case portfolio analysis; consolidation is measured and reported. |

Evidence to collect: architecture diagram showing shared services, SLA documentation for shared infrastructure components, evidence of multiple teams using shared embedding or vector store infrastructure, reference architecture document, platform team charter or on-call rotation.

---

### Dimension 4: Observability and Developer Enablement

This dimension assesses whether teams can see what their AI calls are doing and whether the platform makes it easy to build correctly. Observability without developer enablement produces a platform that is monitored but not adopted; developer tooling without observability produces adoption without accountability. The two are scored together because neither is useful without the other: developers need to know whether their systems are behaving, and the platform team needs to know whether the infrastructure is performing.

| Level | What it looks like |
| --- | --- |
| 1 | No AI observability. Teams discover model failures via user complaints or downstream data errors; no latency or error rate tracking exists; no developer documentation beyond provider docs. |
| 2 | Basic logging exists (API logs retained), but there are no dashboards; developers query logs manually to debug; no developer documentation specific to the internal platform exists. |
| 3 | Observability dashboards exist for core metrics (latency, error rates, token counts by use case); developer documentation covers how to access the platform; but documentation is incomplete and rarely updated. |
| 4 | Observability is comprehensive — latency, token spend, error rates, and quality metrics (where applicable) are dashboard-visible by team and use case; developer documentation is complete, up to date, and includes code examples; a platform SDK or starter kit reduces onboarding time. |
| 5 | Observability feeds automated alerts and triggers incident response when quality thresholds are breached; developer tooling is maintained with a defined review cycle; platform office hours or support channel exists; feedback from developers improves the platform on a cadence. |

Evidence to collect: observability dashboard screenshots, alert configuration for latency or error rate thresholds, developer documentation (with last-updated date), SDK or starter kit repository, evidence that an observability alert triggered an action.

---

### Dimension 5: Build vs. Buy Discipline and Vendor Risk

This dimension assesses whether the organization makes platform decisions deliberately — with documented criteria, recorded rationale, and appropriate vendor contracts — or reactively, based on what individual engineers prefer or what vendors sold. AI vendor risk is distinct from general SaaS vendor risk: model behavior can change without notice, training data provenance affects compliance, and lock-in is harder to reverse than with conventional software. Contracts that do not reflect these realities leave the organization exposed.

| Level | What it looks like |
| --- | --- |
| 1 | No build vs. buy framework. Platform decisions are made based on individual engineers' preferences or vendor sales cycles; no vendor risk program exists for AI tools. |
| 2 | Build vs. buy is considered informally for major decisions, but there is no documented criteria and decisions are not recorded; AI vendor contracts are standard MSAs with no AI-specific terms. |
| 3 | A build vs. buy framework exists with documented criteria; major decisions are recorded with rationale; at least some AI vendor contracts include data processing terms; but model change notification and audit rights are absent from most contracts. |
| 4 | Build vs. buy criteria are applied consistently; decisions are documented with a named approver; AI vendor contracts include model change notification, audit rights (or third-party attestation), data use restrictions, and defined SLAs for model behavior; a vendor risk reassessment cadence is in place. |
| 5 | Vendor selection is driven by TCO analysis that includes lock-in risk and platform portability; contracts are reviewed against a standard AI vendor risk template by legal; vendor risk reassessment is automated as contract renewal triggers; dependency analysis identifies single points of failure in the vendor stack. |

Evidence to collect: build vs. buy framework document, a decision record for a recent platform decision, vendor contract with AI-specific terms highlighted, vendor risk assessment for a critical AI vendor, TCO analysis for a build vs. buy decision.

---

## The Five Maturity Levels

Average the five dimensions for a single maturity level — but treat the average as a label, not the finding. The lowest dimension matters more than the mean.

| Level | Name | Where you are |
| --- | --- | --- |
| 1 | Nascent | No platform infrastructure. AI is deployed through individual team experiments with no shared infrastructure, cost visibility, or governance integration. |
| 2 | Developing | Basic infrastructure exists but is not governed or shared. Cost is invisible, tooling is fragmented, and the same problems are being solved multiple times across the organization. |
| 3 | Emerging | Core platform components are in place but inconsistently used. The platform function exists but has not yet become the default path for new AI projects. This is where most organizations stall. |
| 4 | Scaling | Platform is operational and used by default. Cost is attributed, shared infrastructure is reliable, observability is active, and vendor risk is managed. |
| 5 | Transformational | Platform decisions are driven by portfolio analysis. Infrastructure is continuously optimized, observability feeds automated governance, and the platform proactively enables rather than reactively supports AI projects. |

The gap between Level 3 and Level 4 is where most platform programs stall. Emerging platforms have the components — the gateway exists, the shared embedding service is running, the model registry has entries — but they are not the default. New projects still spin up their own infrastructure because the platform team has not made the shared path easier than the DIY path. Closing that gap requires platform team accountability for onboarding new teams, reference architectures that are genuinely faster to use than to bypass, and a governance mechanism that routes new AI projects through the platform rather than around it.

---

## How to Run the Assessment

**Assemble the right group.** No single function can score all five dimensions honestly. You need the platform or infrastructure lead, representative senior engineers from at least two business-unit AI teams (they know whether the shared infrastructure is actually used), someone from finance with visibility into API spend, and the AI governance owner from Track 02 (vendor risk and model registry overlap with governance). Without engineers from the consuming teams in the room, Dimensions 3 and 4 will be systematically over-scored. The session should run 60–90 minutes.

**Score on evidence, not intent.** For each dimension, rate 1–5 and capture the evidence that supports it — the specific artifacts named in each "Evidence to collect" line. Not "we have a model registry" but "here is the registry document, here are three entries with dated evaluations, and here is the process document for adding a new model." A score inflated by optimism produces a roadmap built on fiction.

**Read the lowest dimension as the binding constraint.** One dimension almost always limits platform effectiveness regardless of strength elsewhere. A Level 4 shared infrastructure program with a Level 1 API governance program means the organization cannot see what the shared infrastructure is costing, which makes every investment decision about expanding it a guess. The binding constraint is what to fix first.

**Act on the shape within 90 days.** For the lowest-scoring dimensions, commit to concrete, owned, measurable actions completable in the next quarter. The assessment is only valuable if it changes what gets funded and assigned. If it produces a slide and a meeting note, it was not worth running.

---

## Scoring Template

Use this in your assessment session:

| Dimension | Score (1–5) | Supporting evidence | Key gap | 90-day action |
| --- | --- | --- | --- | --- |
| API Governance and Cost Visibility | | | | |
| Model Registry and Selection Discipline | | | | |
| Shared Infrastructure and Tooling Consolidation | | | | |
| Observability and Developer Enablement | | | | |
| Build vs. Buy Discipline and Vendor Risk | | | | |
| **Average** | | | | |

**Interpreting the average:**

- **1.0–2.0:** Platform infrastructure is not functional. Do not scale AI deployment — the cost, quality, and vendor risk exposure accumulating across fragmented teams is not visible and cannot be managed.
- **2.0–3.0:** Platform infrastructure exists but is not operational. Identify the binding constraint (usually API governance or shared infrastructure) and fix it before funding net-new AI capabilities.
- **3.0–4.0:** Platform is real but inconsistently used. Build systematically toward making the shared path the default path; raise the lowest dimension first.
- **4.0–5.0:** Platform is operational. Focus on automation, portfolio-driven optimization, and tighter integration with the governance function in Track 02.

---

## What to Do With the Results

The most common failure mode: the assessment produces a score, someone presents it in a platform review, and it is filed. The score is not the output — the constraint identification and the 90-day actions are. If the lowest-scoring dimension does not have a named owner and a funded workstream within two weeks of the session, the assessment will not change anything.

**Use the results to gate downstream investment, not just to plan platform work.** A low score on API Governance (Dimension 1) means every other platform investment is building on sand: the organization cannot see what the platform is costing, cannot attribute spend to the teams generating it, and cannot detect runaway consumption before it becomes a budget crisis. Dimension 1 is often the quickest win — deploying a centralized gateway with per-team attribution is an infrastructure project with a defined finish line — and it is the most important foundation. Nothing else the platform does is legible without it.

**Platform maturity gaps frequently surface ownership voids that were invisible before.** When an organization runs this assessment and discovers a Level 1 or 2 model registry, the usual finding is not that the problem was unknown — it is that no one owned it. Engineering assumed it was a governance function; governance assumed engineering handled it; procurement assumed it was a technical matter. The assessment forces a conversation about who actually owns each dimension. Those ownership assignments, made explicit and committed to in writing, are often the most durable output of the exercise.

**Feed the lowest-scoring dimensions into the platform team's sprint priorities.** Whatever team or function owns the AI platform — whether a dedicated ML platform team or a combined data and infrastructure group — the lowest-scoring dimensions should be active work items until they reach Level 3 or above. The re-score date — typically 90 days after the initial assessment — should be on the calendar before the session ends. A platform function that does not track its own maturity has no mechanism to improve.

---

## Sources

- McKinsey & Company — *The State of AI* — 2025
- Gartner — *Hype Cycle for Artificial Intelligence* — 2024/2025
- Anthropic — *Prompt Caching Documentation* — 2024
- Databricks — *State of Data + AI Report* — 2024
- IDC — *Worldwide AI and GenAI Spending Guide* — 2025
- CNCF — *Cloud Native AI White Paper* — 2024
