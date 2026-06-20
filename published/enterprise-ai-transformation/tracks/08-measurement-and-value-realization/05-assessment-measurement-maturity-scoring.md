---
type: Playbook
title: "Assessment: Measurement Maturity Scoring"
description: "A scoring assessment for measurement maturity across instrumentation coverage, attribution capability, and feedback-loop effectiveness, with level definitions and a remediation path."
tags: [measurement, assessment, maturity-scoring, playbook]
timestamp: "2026-06-18"
---

## What This Is For

This assessment tells you where your organization actually stands on AI *measurement* — not how many dashboards you have, but whether you can tie AI to value, prove it to finance, and act on what you learn. It is the scoring companion to the [measurement framework](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md) (the argument), the [attribution methodology](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/03-attribution-methodology.md) (which isolates AI's contribution from confounders), and the [practitioner guide to standing up AI measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/04-practitioner-guide-standing-up-ai-measurement.md) (which builds the capability). Score before you launch a measurement program, to find the binding constraint; score again on a cadence, to see whether it is moving.

A dedicated measurement score is needed because measurement is the gap between piloting and value — and the place most organizations are weakest. MIT's NANDA initiative found **95% of enterprise gen-AI pilots delivered no measurable P&L impact** ([MIT Project NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)), and **at least 30% of gen-AI projects are projected to be abandoned after proof of concept by the end of 2025**, unclear business value among the reasons ([Gartner, 2024](#ev-gartner-genai-poc-2024-abandonment)). The problem is rarely the model; it is that no one defined success, instrumented for it, or attributed the result. A score that counts dashboards would miss all of this; a score that counts whether AI's value reaches the CFO tells the truth.

This page gives you five scoring dimensions, a 1–5 maturity ladder for each, calibration benchmarks, and a method for interpreting the result.

---

## How to Use It

1. **Score each of the five dimensions 1–5** using the ladders below, evidenced by real artifacts — metric definitions, telemetry coverage, attribution analyses, CFO reports — not by impression.
2. **Plot a profile, not an average.** A single low dimension is a bottleneck even when the mean looks healthy.
3. **Locate the gap by use case.** Break coverage down by use case and business unit so you can see *where* measurement is thin.
4. **Interpret the pattern** (final section) and point fixes at the relevant step of [standing up AI measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/04-practitioner-guide-standing-up-ai-measurement.md).

The five-level structure follows established maturity-model convention — the same **Initial → Optimizing** progression as the CMMI tradition — so a measurement score is comparable to how the organization already reasons about other capabilities. The ladder names below (Blind → Tracking → Attributing → Acting → Optimizing) name the *measurement* version of that climb.

---

## The Five Dimensions

| # | Dimension | The question it answers |
|---|---|---|
| D1 | Instrumentation Coverage | Do AI use cases have defined success metrics and telemetry in place at deployment? |
| D2 | Baseline & KPI Definition | Are KPIs and baselines defined *before* launch, with targets? |
| D3 | Attribution Capability | Can the org tie AI to financial/EBIT impact, isolate it from confounders, and report it to finance? |
| D4 | Feedback-Loop Effectiveness | Does measurement drive reallocation — scaling winners, killing losers, redesigning workflows? |
| D5 | Governance & Cadence | Who owns measurement, on what rhythm, with what leadership and CFO involvement? |

---

## The 1–5 Maturity Ladder

Each dimension climbs the same five rungs — **1 Blind → 2 Tracking → 3 Attributing → 4 Acting → 5 Optimizing** — but the descriptor changes per dimension.

### D1 — Instrumentation Coverage

| Level | What it looks like |
| --- | --- |
| 1 — Blind | No success metrics defined; use cases ship dark; telemetry absent. |
| 2 — Tracking | Usage/activity logged for some use cases, but metrics bolted on after launch and uneven. |
| 3 — Attributing | Most priority use cases have defined success metrics and telemetry in place at deployment. |
| 4 — Acting | Instrumentation is a launch gate; coverage tracked by use case and business unit. |
| 5 — Optimizing | Full coverage by design; metric and telemetry definitions versioned and refreshed as use cases evolve. |

### D2 — Baseline & KPI Definition

| Level | What it looks like |
| --- | --- |
| 1 — Blind | No baselines; no KPIs; "it feels faster" is the only evidence. |
| 2 — Tracking | KPIs named after the fact; baselines reconstructed retrospectively, if at all. |
| 3 — Attributing | KPIs and pre-launch baselines defined for priority use cases, with explicit targets. |
| 4 — Acting | Baseline-and-target is a standard pre-launch artifact; targets reviewed against actuals. |
| 5 — Optimizing | Baselines and KPIs are continuous and standardized; targets recalibrated as the business changes. |

### D3 — Attribution Capability

| Level | What it looks like |
| --- | --- |
| 1 — Blind | No attempt to tie AI to outcomes; impact unknown. |
| 2 — Tracking | Anecdotes and self-reported time savings; no isolation from confounders. |
| 3 — Attributing | A repeatable [attribution method](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/03-attribution-methodology.md) (controls, holdouts) isolates AI's contribution for priority use cases. |
| 4 — Acting | Financial/EBIT impact attributed and reported to finance on a regular cadence. |
| 5 — Optimizing | Attribution is finance-grade and continuous; AI value is a line the CFO trusts and forecasts against. |

### D4 — Feedback-Loop Effectiveness

| Level | What it looks like |
| --- | --- |
| 1 — Blind | Results never reviewed; nothing scaled or killed on evidence. |
| 2 — Tracking | Metrics reported but rarely change decisions; losers linger, winners stall. |
| 3 — Attributing | Measurement informs go/no-go on individual use cases; some winners scaled. |
| 4 — Acting | Measurement drives reallocation — winners scaled, losers killed, [workflows redesigned](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md) on the evidence. |
| 5 — Optimizing | A standing portfolio loop continuously reallocates spend and effort toward measured value. |

### D5 — Governance & Cadence

| Level | What it looks like |
| --- | --- |
| 1 — Blind | No owner; no reporting rhythm; leadership unaware of AI value. |
| 2 — Tracking | Ownership ambiguous; ad-hoc reporting; finance not in the loop. |
| 3 — Attributing | A named owner and a regular reporting cadence exist; results reach leadership. |
| 4 — Acting | Measurement governed with CFO/finance involvement and a fixed cadence tied to decisions. |
| 5 — Optimizing | Value realization is a board-level operating rhythm; finance and the business co-own the numbers. |

---

## Calibration Benchmarks

Use these to judge where "most organizations" sit, so a score reflects reality rather than optimism:

- **KPI discipline is rare.** **Fewer than one in five organizations track well-defined KPIs for their gen-AI solutions** ([McKinsey, 2025](#ev-mckinsey-rewiring-2025-kpi-tracking)), and while **48% report using specific KPIs to evaluate gen-AI**, **41% have struggled to define and measure the exact impacts** ([Deloitte, 2024](#ev-deloitte-state-genai-2024-specific-kpis); [Deloitte, 2024](#ev-deloitte-state-genai-2024-measure-impacts-struggle)). Most organizations score **D1–D2 ≤ 2** until they act.
- **Attribution rarely reaches finance.** Only **39% attribute any EBIT impact to AI** ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-ebit-any)), and just **16% produce regular CFO reports on the value created** ([Deloitte, 2024](#ev-deloitte-state-genai-2024-cfo-reports)). A **D3 of 4–5 is uncommon** and should be evidenced with real finance-reviewed numbers.
- **Feedback loops are the differentiator.** Workflow redesign is the practice most correlated with EBIT impact, **yet only about 21% have redesigned any workflows** ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-workflow-redesign)). Leading "future-built" firms **rigorously track AI value at more than 60%, versus only 17% of stagnating firms** — roughly **3.5x** more often ([BCG, 2025](#ev-bcg-value-gap-2025-track-value-leaders-laggards)) — but only **5% of firms are future-built** ([BCG, 2025](#ev-bcg-value-gap-2025-distribution)). Among high-AI-maturity organizations, **63% run financial/ROI analysis and concretely measure customer impact** ([Gartner, 2025](#ev-gartner-ai-maturity-2025-roi-analysis)).
- **The result of weak measurement.** **95% of enterprise gen-AI pilots delivered no measurable P&L impact** ([MIT Project NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)), and **more than two-thirds of organizations expect 30% or fewer of their gen-AI experiments to be fully scaled in the next 3–6 months** ([Deloitte, 2025](#ev-deloitte-state-genai-2025-scale-expectations)). Only about **6% of organizations are high performers attributing more than 5% of EBIT to AI** ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-high-performers)). A composite measurement score of 4–5 is rare and should be evidenced hard.

---

## Interpreting the Result

Read the *pattern*, not the average. Common profiles and their fixes:

| Pattern | What it means | Where to act |
| --- | --- | --- |
| High D1, low D2 | Telemetry exists but with no baselines or targets — data with no yardstick. | Define KPIs and pre-launch baselines (see [standing up AI measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/04-practitioner-guide-standing-up-ai-measurement.md)). |
| Decent D1–D2, low D3 | You can see usage but cannot prove value or isolate it — the "dashboards, no dollars" trap. | Apply the [attribution methodology](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/03-attribution-methodology.md); get a number to finance. |
| High D3, low D4 | Impact is measured but nothing changes — measurement as reporting theater. | Stand up the portfolio loop; scale winners, kill losers, [redesign workflows](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md). |
| Low D5 across the board | No owner, no cadence, finance absent — every other dimension will erode. | Name an owner, set a cadence, bring in the CFO. |
| Flat 2s everywhere | Activity logged, value unproven — the modal organization. | Define baselines and targets, then build attribution from the [measurement framework](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md) up. |

Measurement gates value realization itself: a low score here means you cannot tell whether any other track is working, so the **lowest dimension is the binding constraint** — fix it before trusting the rest of the program's numbers.

---

## Key Takeaways

- **Score whether value reaches the CFO, not how many dashboards exist.** KPI discipline is rare — fewer than one in five orgs track well-defined gen-AI KPIs ([McKinsey, 2025](#ev-mckinsey-rewiring-2025-kpi-tracking)), and only 16% report value to the CFO regularly ([Deloitte, 2024](#ev-deloitte-state-genai-2024-cfo-reports)).
- **Five dimensions:** instrumentation coverage, baseline & KPI definition, attribution capability, feedback-loop effectiveness, and governance & cadence.
- **Read the profile, not the average** — the lowest dimension is the binding constraint, and "dashboards, no dollars" (good D1–D2, weak D3) is the most common false-positive.
- **Calibrate against reality:** only 39% attribute any EBIT to AI ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-ebit-any)), leading firms track value ~3.5x more often than laggards ([BCG, 2025](#ev-bcg-value-gap-2025-track-value-leaders-laggards)), and 95% of pilots show no measurable P&L impact ([MIT Project NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)).
- **Measurement gates value realization** — without it you cannot tell whether any track is working, so fix the binding dimension before trusting the program's numbers.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **MIT Project NANDA — *The GenAI Divide: State of AI in Business 2025*, 2025.** Just 5% of integrated AI pilots are extracting millions in value, while the vast majority remain stuck with no measurable P&L impact. [View source](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf){#ev-mit-nanda-genai-divide-2025-no-pl-impact} · verified 2026-06-20 · ⚠ secondary mirror
- **Gartner — *Gartner Predicts 30% of Generative AI Projects Will Be Abandoned After Proof of Concept By End of 2025*, 2024.** At least 30% of generative AI projects will be abandoned after proof of concept by the end of 2025, due to poor data quality, inadequate risk controls, escalating costs or unclear business value. [View source](https://www.gartner.com/en/newsroom/press-releases/2024-07-29-gartner-predicts-30-percent-of-generative-ai-projects-will-be-abandoned-after-proof-of-concept-by-end-of-2025){#ev-gartner-genai-poc-2024-abandonment} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI: How Organizations Are Rewiring to Capture Value*, 2025.** Less than one in five organizations are tracking KPIs for gen AI solutions — and tracking well-defined KPIs is the practice with the most impact on the bottom line. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-how-organizations-are-rewiring-to-capture-value){#ev-mckinsey-rewiring-2025-kpi-tracking} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** Organizations are using specific KPIs for evaluating GenAI performance (48%). [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-specific-kpis} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** 41% have struggled to define and measure the exact impacts of their GenAI efforts. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-measure-impacts-struggle} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI*, 2025.** About 39% of organizations report any enterprise-level EBIT impact from AI; most of those say less than 5% of EBIT is attributable to AI use. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-ebit-any} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** Only 16% have produced regular reports for the CFO about the value being created with GenAI. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-cfo-reports} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI*, 2025.** 21% of respondents reporting gen AI use say their organizations have fundamentally redesigned at least one workflow; redesigning workflows has the biggest effect on an organization's ability to see EBIT impact from gen AI. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-workflow-redesign} · verified 2026-06-20 · primary
- **BCG — *The Widening AI Value Gap*, 2025.** More than 60% of future-built firms systematically measure and report AI value, compared with only 17% of stagnating companies. [View source](https://media-publications.bcg.com/The-Widening-AI-Value-Gap-Sept-2025.pdf){#ev-bcg-value-gap-2025-track-value-leaders-laggards} · verified 2026-06-20 · ⚠ secondary mirror
- **BCG — *The Widening AI Value Gap*, 2025.** Only about 5% of companies (the 'future-built') are generating value at scale, while 60% of companies are laggards with little or no value; 35% are in between. [View source](https://media-publications.bcg.com/The-Widening-AI-Value-Gap-Sept-2025.pdf){#ev-bcg-value-gap-2025-distribution} · verified 2026-06-20 · primary
- **Gartner — *Gartner Survey on Organizations With High AI Maturity*, 2025.** Almost two thirds (63 percent) of leaders from high-maturity organizations run financial analysis on risk factors, conduct ROI analysis and concretely measure customer impact. [View source](https://www.gartner.com/en/newsroom/press-releases/2025-06-30-gartner-survey-finds-forty-five-percent-of-organizations-with-high-artificial-intelligence-maturity-keep-artificial-intelligence-projects-operational-for-at-least-three-years){#ev-gartner-ai-maturity-2025-roi-analysis} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Generating a new future (Q4)*, 2025.** More than two-thirds of respondents say that 30% or fewer of their experiments will be fully scaled in the next three to six months. [View source](https://www.prnewswire.com/news-releases/the-path-to-sustainable-generative-ai-value-balances-passion-pragmatism-and-patience-finds-new-deloitte-survey-302355026.html){#ev-deloitte-state-genai-2025-scale-expectations} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI*, 2025.** Respondents who attribute EBIT impact of 5 percent or more to AI use and say their organization has seen significant value from AI — about 6 percent of respondents — are defined as AI high performers. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-high-performers} · verified 2026-06-20 · primary
