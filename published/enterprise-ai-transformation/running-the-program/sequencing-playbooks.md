---
type: Playbook
title: Sequencing Playbooks
description: Four sequencing archetypes with recommended track prioritization and pacing for different organization types.
tags: [program-management, sequencing, playbook]
timestamp: "2026-06-19"
---

The eight-track model has no universal running order. The numbers `01` through `08` are a *reading* order, not an *execution* order — and the single most expensive mistake a transformation makes is to treat them as the latter, finishing Strategy before touching Governance before touching Data, and shipping nothing to a real user for two years. The [framework architecture](/enterprise-ai-transformation/framework-architecture.md) establishes the rule this page operates under: **sequence by dependency, not by track number**, and run every track *concurrently but at staggered intensity* — some activity everywhere early (even if only assessment), heavy investment only where the upstream dependency is ready enough to pay off.

> **The core rule.** Find your binding constraint — the lowest, most upstream track that is throttling everything downstream of it — and pour resources *there*, not into the most visible or fashionable layer. The same eight tracks, sequenced against a different binding constraint, produce four very different programs. This page expands the architecture's [sequencing-by-organization-type table](/enterprise-ai-transformation/framework-architecture.md) into four full playbooks.

The stakes for getting the order right are not abstract. Gartner predicted that at least 30% of generative-AI projects would be abandoned after proof of concept by the end of 2025 — naming poor data quality, inadequate risk controls, escalating costs, and unclear business value as the causes, and warning that the risk *grows as the scope of initiatives widens* ([Gartner, 2024](#ev-gartner-genai-poc-2024-abandonment)). MIT's study of enterprise deployments was blunter: roughly 95% of enterprise gen-AI pilots delivered no measurable P&L impact, and the implementations that succeeded focused on narrow, workflow-specific use cases rather than broad rollouts ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)). BCG put the scaling gap at its starkest — only about 5% of companies are achieving AI value at scale, while around 60% see no material value at all ([BCG, 2025](#ev-bcg-value-gap-2025-distribution)). Sequencing is how you land in the 5%, not the 95%.

Each playbook below gives the org profile, its usual binding constraint, a recommended track sequence, a pacing grid across the first few quarters, and the top risk to watch.

## Archetype 1 — Large Enterprise (complex, multi-business-unit)

**Profile.** Many business units, established (often regulated) governance, deep legacy data estates, thousands of employees, competing internal agendas. The hard problem is not capability but coordination: scaling across units without either fragmenting into uncoordinated pilots or collapsing under central-program overhead. McKinsey found that while only about a third of organizations have begun scaling AI across the enterprise, larger companies are the *most* likely to have reached the scaling phase — they have the resources, but also the most surface area to coordinate ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-scaling-by-size)).

**Binding constraint.** Governance and platform coherence. With multiple units buying their own tools, the constraint is rarely "can we build AI" — it is "can we build it once, safely, and reuse it." Direction ([AI Strategy & Leadership](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/index.md), [AI Governance & Risk](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/index.md)) must be real, and Foundation ([Technology Architecture & Platform](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/index.md)) must be shared, or the enterprise pays for the same point solution ten times and cannot pass an audit on any of them.

**Recommended sequence.** `01` (light but funded) → `02` + `04` in parallel to lay shared guardrails and a shared platform → `03` on the priority data domains → then `05`/`06`/`07` piloted in *one or two lead business units*, with `08` instrumented from day one. Let the lead-unit evidence pull the next unit in, rather than mandating all units at once.

| Quarter | High intensity | Active / assessment-only |
| --- | --- | --- |
| Q1 | 01 Strategy, 02 Governance | 03 Data, 04 Platform, 08 Measurement (baseline) |
| Q2 | 02 Governance, 04 Platform | 03 Data (priority domains), 01 (refresh) |
| Q3 | 04 Platform, 05 Workflow (lead BU) | 06 Adoption, 07 Talent (lead BU), 08 |
| Q4 | 05/06/07 (lead BU), 08 Measurement | 01 (reprioritize on evidence), expand to BU #2 |

*Numbers are track #s — see the [eight-track key](/enterprise-ai-transformation/framework-architecture.md#what-each-track-owns).*

**Top risk: boil-the-ocean.** The large enterprise has the budget to stand up all eight tracks at full intensity at once — which is exactly the "too parallel" failure mode. Teams thrash, work is duplicated across units, and foundation gaps surface only after execution has been built on top of them. Resist the urge to launch everywhere; prove the pattern in a lead unit and let [Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md) pace the rollout. See the [program architecture](/enterprise-ai-transformation/running-the-program/program-architecture.md) for the operating model that keeps central guardrails and unit autonomy in balance.

## Archetype 2 — Mid-Market (resource-constrained, high urgency)

**Profile.** Hundreds to low-thousands of employees, lean teams, a small or no dedicated AI function, real budget and talent limits, and acute competitive urgency. The adoption gap is real: large firms use AI at more than three times the rate of small firms (40% vs 11.9%) ([OECD, 2025](#ev-oecd-2025-firm-size-adoption-gap)), and around 44% of small businesses report lacking the resources and expertise to adopt AI at all ([Goldman Sachs, 2025](#ev-goldman-sachs-2025-smb-resource-gap)). But the mid-market's structural advantage is speed — fewer silos and shorter approval chains let it realize value faster, and the gap is now closing in months rather than the years that prior technology cycles took.

**Binding constraint.** Focus and talent. The mid-market cannot run eight tracks; it must pick the one or two highest-leverage workflows and resource them properly. Spreading a thin team across all tracks guarantees that none reaches the threshold where value appears.

**Recommended sequence.** `01` (very light — pick *one* business outcome) → `05` on a single high-value workflow, using a bought platform rather than a built one (externally sourced tools reached deployment at roughly twice the rate of internal builds in MIT's data) ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-buy-vs-build)) → `06`/`07` tightly coupled to that one workflow → `08` to prove it → only then widen. [AI Governance & Risk](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/index.md) and [Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md) are addressed *just enough* for the chosen use case, not enterprise-wide.

| Quarter | High intensity | Active / assessment-only |
| --- | --- | --- |
| Q1 | 01 (one outcome), 05 Workflow (one use case) | 02/03 (scoped to the use case), 08 baseline |
| Q2 | 05 Workflow, 06 Adoption, 07 Talent | 08 Measurement |
| Q3 | 08 Measurement (prove value), 06 Adoption | 01 (decide whether to widen) |
| Q4 | Widen to use case #2 *only if #1 proved out* | 02/03/04 (extend as needed) |

*Numbers are track #s — see the [eight-track key](/enterprise-ai-transformation/framework-architecture.md#what-each-track-owns).*

**Top risk: spreading too thin.** With a lean team, the temptation is to dabble in everything and finish nothing. The fix is ruthless single-threading — one workflow, fully resourced through to measured value, before the second. Buy rather than build to preserve the scarce engineering talent for integration, not infrastructure. The [90-day launch](/enterprise-ai-transformation/running-the-program/the-90-day-launch.md) is calibrated for exactly this tempo.

## Archetype 3 — Single-Function Deployment (narrow scope, fast cycle)

**Profile.** One function (support, sales, engineering, finance) deploying AI into its own workflow, often inside a larger organization, with a short cycle and a clear owner. This is the highest-yield shape in the data: MIT's winners were precisely the teams that focused on *narrow, workflow-specific use cases with clearly defined operational outcomes* ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)), and IDC/Microsoft found organizations realizing value within about 13 months of deployment, with deployments themselves taking under 8 months ([IDC, 2024](#ev-idc-2024-deployment-and-time-to-value)).

**Binding constraint.** Adoption and proof. The technology and the workflow are well understood; what decides success is whether the function's people actually change how they work, and whether the win is measured credibly enough to defend and expand. McKinsey found only about 21% of gen-AI users have redesigned any workflow — most simply layer AI on top of existing process — yet high performers are 2.8x more likely to have fundamentally redesigned theirs (55% vs 20%) ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-workflow-redesign); [McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-workflow-redesign-highperf)).

**Recommended sequence.** `05` (redesign the one workflow, not just bolt AI onto it) → `06` + `07` in lockstep so the function adopts and is enabled together → `08` from day zero to capture a clean baseline and a defensible delta. [AI Strategy & Leadership](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/index.md), [AI Governance & Risk](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/index.md), [Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md), and [Technology Architecture & Platform](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/index.md) are *inherited* from the parent org or scoped to the single use case — this archetype consumes foundation rather than building it.

| Quarter | High intensity | Active / assessment-only |
| --- | --- | --- |
| Q1 | 05 Workflow redesign, 08 baseline | 02/03/04 (inherit / scope), 06 readiness |
| Q2 | 06 Adoption, 07 Talent, 05 | 08 Measurement (early signal) |
| Q3 | 08 Measurement (attribute value), 06 | 01 (make the case to expand) |

*Numbers are track #s — see the [eight-track key](/enterprise-ai-transformation/framework-architecture.md#what-each-track-owns).*

**Top risk: a pilot that proves nothing.** A narrow deployment that never captures a baseline, or that measures share-of-output ("X% of work used AI") instead of outcomes, ends as one of the 95% with no measurable P&L impact ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)). Instrument [Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md) *before* go-live and tie the win to a real before/after delta — see the [attribution methodology](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/03-attribution-methodology.md) for the counterfactual discipline this requires.

## Archetype 4 — Greenfield (new org or division, building from scratch)

**Profile.** A new company, a new division, or a clean-sheet business unit with no legacy estate, no entrenched tooling, and no incumbent process to defend. The rare luxury is genuine choice of order — and the rare trap is mistaking the absence of legacy for the absence of foundations. There is no data to clean, but also no data, no governance, no platform, and no people yet.

**Binding constraint.** Foundations-by-design. Because nothing exists, the constraint is building the substrate *correctly the first time* — AI-ready data contracts, governance, and a platform baked in from the start — rather than retrofitting them later. This is the one archetype where investing early and deliberately in Foundation ([Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md), [Technology Architecture & Platform](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/index.md)) is not over-engineering; it is the entire advantage of being greenfield.

**Recommended sequence.** `01` to set intent and the operating model → `02` + `04` + `03` built *AI-native from the start* (data products with lineage and contracts, a self-serve platform, governance as a platform property rather than a committee) → `07` to hire and shape roles around human-AI collaboration → `05`/`06` as the work and the team come online → `08` instrumented as a first-class system, not an afterthought.

| Quarter | High intensity | Active / assessment-only |
| --- | --- | --- |
| Q1 | 01 Strategy, 02 Governance, 04 Platform | 03 Data (design), 07 Talent (hiring plan) |
| Q2 | 03 Data, 04 Platform, 07 Talent | 05 Workflow (design), 08 (instrument) |
| Q3 | 05 Workflow, 06 Adoption, 07 Talent | 08 Measurement |
| Q4 | 05/06, 08 Measurement | 01 (refine on first evidence) |

*Numbers are track #s — see the [eight-track key](/enterprise-ai-transformation/framework-architecture.md#what-each-track-owns).*

**Top risk: waterfall transformation.** The greenfield's freedom to build foundations first can curdle into the "too sequential" failure mode — perfecting the platform and the data architecture for a year while shipping nothing and learning nothing. Even here, run a thin slice of execution ([Workflow Optimization & Automation](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/index.md), [AI Adoption & Culture](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/index.md)) and measurement ([Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md)) early so the foundation is shaped by real usage, not by speculation. Build the substrate deliberately, but never in isolation from a live use case.

## How to Choose Your Archetype

These four are anchors, not boxes — most real organizations sit between two of them (a mid-market firm with a regulated profile; a large enterprise running a single-function pilot inside one unit). Choose by **binding constraint, not by self-description**:

- If coordination and reuse across units is what's hurting → **Large Enterprise**.
- If a lean team and urgency force hard focus → **Mid-Market**.
- If one function owns the whole cycle and just needs to prove a win → **Single-Function**.
- If you are building from a clean sheet → **Greenfield**.

Do not pick by intuition. Run the [integrated assessment](/enterprise-ai-transformation/running-the-program/integrated-assessment.md) to score all eight tracks on the **1 Nascent · 2 Developing · 3 Emerging · 4 Scaling · 5 Transformational** ladder, then read the spread. A *spiky* profile (a 4 next to a 1) names your binding constraint directly: the high track is being throttled by the low one. A *flat-but-low* profile (everything at 2) means no track has crossed the value threshold — concentrate, don't spread. The assessment turns "which archetype are we?" into evidence rather than a guess, and re-running it on a cadence is how the sequence adapts as the constraint moves.

## Key Takeaways

- **Sequence by dependency, not by track number.** The `01`–`08` numbering is a reading order; the execution order is whatever relieves your binding constraint first.
- **Run concurrently at staggered intensity.** Some activity in every track early (even just assessment); heavy investment only where the upstream dependency is ready. Avoid both failure modes — waterfall ("too sequential") and boil-the-ocean ("too parallel").
- **The constraint differs by archetype.** Large enterprises stall on coordination/platform coherence; mid-market on focus/talent; single-function on adoption/proof; greenfield on building foundations right the first time.
- **Narrow and proven beats broad and unproven.** ~95% of gen-AI pilots show no P&L impact, and the winners run narrow, workflow-specific use cases ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)); only ~5% of companies reach value at scale ([BCG, 2025](#ev-bcg-value-gap-2025-distribution)).
- **Let [Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md) pace the next move.** Instrument it from day zero, prove the first win, and let the evidence pull the next investment.
- **Choose your archetype from the [integrated assessment](/enterprise-ai-transformation/running-the-program/integrated-assessment.md)**, not from intuition — the spread of track scores names your binding constraint.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Gartner — *Gartner Predicts 30% of Generative AI Projects Will Be Abandoned After Proof of Concept By End of 2025*, 2024.** At least 30% of generative AI projects will be abandoned after proof of concept by the end of 2025, due to poor data quality, inadequate risk controls, escalating costs or unclear business value. [View source](https://www.gartner.com/en/newsroom/press-releases/2024-07-29-gartner-predicts-30-percent-of-generative-ai-projects-will-be-abandoned-after-proof-of-concept-by-end-of-2025){#ev-gartner-genai-poc-2024-abandonment} · verified 2026-06-20 · primary
- **MIT Project NANDA — *The GenAI Divide: State of AI in Business 2025*, 2025.** Just 5% of integrated AI pilots are extracting millions in value, while the vast majority remain stuck with no measurable P&L impact. [View source](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf){#ev-mit-nanda-genai-divide-2025-no-pl-impact} · verified 2026-06-20 · ⚠ secondary mirror
- **BCG — *The Widening AI Value Gap*, 2025.** Only about 5% of companies (the 'future-built') are generating value at scale, while 60% of companies are laggards with little or no value; 35% are in between. [View source](https://media-publications.bcg.com/The-Widening-AI-Value-Gap-Sept-2025.pdf){#ev-bcg-value-gap-2025-distribution} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI in 2025*, 2025.** About one-third of organizations have begun to scale AI across the enterprise; larger companies are the most likely to have reached the scaling phase. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-scaling-by-size} · verified 2026-06-20 · primary
- **OECD — *AI adoption by small and medium-sized enterprises*, 2025.** 40% of firms with 250 or more employees used AI in 2024, versus only 11.9% of firms with 10 to 49 employees; large firms are more than three times as likely to use AI as small firms. [View source](https://www.oecd.org/en/publications/2025/12/ai-adoption-by-small-and-medium-sized-enterprises_9c48eae6.html){#ev-oecd-2025-firm-size-adoption-gap} · verified 2026-06-20 · primary
- **Goldman Sachs — *10,000 Small Businesses Voices (AI survey)*, 2025.** 44% of small business owners said they do not have access to the resources and expertise necessary to successfully deploy AI. [View source](https://www.goldmansachs.com/community-impact/10000-small-businesses-voices/insights/ai-presents-a-major-opportunity-for-small-businesses){#ev-goldman-sachs-2025-smb-resource-gap} · verified 2026-06-20 · primary
- **MIT Project NANDA — *The GenAI Divide: State of AI in Business 2025*, 2025.** Tools sourced from external vendors reached deployment about twice as often as internally built tools (roughly 67% vs 33%). [View source](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf){#ev-mit-nanda-genai-divide-2025-buy-vs-build} · verified 2026-06-20 · ⚠ secondary mirror
- **IDC — *The Business Opportunity of AI (IDC InfoBrief, sponsored by Microsoft)*, 2024.** AI deployments take less than 8 months on average and organizations realize value within 13 months. [View source](https://blogs.microsoft.com/blog/2024/11/12/idcs-2024-ai-opportunity-study-top-five-ai-trends-to-watch/){#ev-idc-2024-deployment-and-time-to-value} · verified 2026-06-20 · ⚠ secondary mirror
- **McKinsey — *The State of AI*, 2025.** 21% of respondents reporting gen AI use say their organizations have fundamentally redesigned at least one workflow; redesigning workflows has the biggest effect on an organization's ability to see EBIT impact from gen AI. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-workflow-redesign} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI in 2025*, 2025.** AI high performers are 2.8 times more likely to report fundamental workflow redesign than other organizations (55% versus 20%). [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-workflow-redesign-highperf} · verified 2026-06-20 · primary
