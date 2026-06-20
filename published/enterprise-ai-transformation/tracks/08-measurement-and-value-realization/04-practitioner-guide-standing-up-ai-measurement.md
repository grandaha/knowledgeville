---
type: Playbook
title: "Practitioner Guide: Standing Up AI Measurement"
description: "How to instrument AI initiatives before deployment, define success metrics per use case, build measurement infrastructure, set a reporting cadence, and use measurement to drive roadmap decisions."
tags: [measurement, practitioner-guide, instrumentation, playbook]
timestamp: "2026-06-18"
---

Most AI programs measure too late, too little, or not at all. Fewer than one in five organizations track well-defined KPIs for their gen-AI solutions — and KPI tracking is among the practices most correlated with bottom-line impact ([McKinsey, 2025](#ev-mckinsey-rewiring-2025-kpi-tracking)). The cost of that gap shows up downstream: only 47% of IT decision-makers say their company is currently achieving positive ROI from its AI projects ([IBM, 2024](#ev-ibm-ai-roi-2024-positive-roi)), only 26% of companies have moved beyond proof-of-concept to generate tangible value ([BCG, 2024](#ev-bcg-value-2024-beyond-poc)), and Gartner projects that at least 30% of gen-AI projects will be abandoned after proof of concept by the end of 2025 — driven by poor data quality, weak risk controls, escalating cost, and unclear value ([Gartner, 2024](#ev-gartner-genai-poc-2024-abandonment)). Measurement is what lets you catch those failures early and reallocate before the money is gone.

This guide is the operational companion to the [measurement framework](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md). The framework tells you *what* a good measurement system contains; this guide walks you through *standing one up*, step by step.

> If you can't measure the baseline before you ship, you can't prove the value after — instrument first, deploy second.

## Before You Start

The single most expensive mistake in AI measurement is reconstructing a baseline after the fact. Once a tool is live, the "before" state is gone: people have changed how they work, the old process metrics have drifted, and any number you produce later is an estimate you'll spend months defending. The discipline is simple to state and hard to enforce: **instrument before deployment, and capture a baseline you cannot recreate later.**

Before the first user touches the system:

- [ ] Name the use case and the single business problem it solves.
- [ ] Capture the pre-AI baseline — cycle time, cost per task, error rate, volume — for the exact workflow you're changing.
- [ ] Decide how you'll attribute change to the AI versus everything else moving at the same time (see [attribution methodology](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/03-attribution-methodology.md)).
- [ ] Confirm you can log the events you'll need (usage, acceptance, outcome) — not someday, but on day one.

If any box is unchecked, you are not ready to deploy. The context here is sobering: 41% of organizations have struggled to define and measure the exact impacts of gen-AI, and only 16% produce regular CFO reports on the value created ([Deloitte, 2024](#ev-deloitte-state-genai-2024-measure-impacts-struggle); [Deloitte, 2024](#ev-deloitte-state-genai-2024-cfo-reports)). The teams that escape that trap are the ones that decided what to measure before they had anything to measure it on.

## Step 1 — Define Success Metrics Per Use Case

Don't start with metrics. Start with goals, and let the metrics fall out. The cleanest method is Google's **Goals–Signals–Metrics (GSM)** approach, paired with the **HEART framework** (Happiness, Engagement, Adoption, Retention, Task success) ([Google, 2010](#ev-google-gsm-heart-2010-framework)). For each use case:

1. **Goal** — what success looks like in plain language ("support agents resolve tickets faster without lowering quality").
2. **Signals** — observable behaviors or outcomes that indicate progress toward the goal (agents accept AI-drafted replies; resolution time drops; CSAT holds).
3. **Metrics** — the specific numbers you'll track for each signal (acceptance rate, median handle time, CSAT delta).

Then pick **one north-star metric** driven by **3–5 input metrics** ([Amplitude, 2024](#ev-amplitude-north-star-metric-framework)). The north star is the single output that best expresses the value of the use case; the input metrics are the levers a team can actually move week to week. Resist the urge to name ten north stars — a program with ten north stars has none.

For broader product-style adoption framing, **AARRR / "Pirate Metrics"** (Acquisition, Activation, Retention, Referral, Revenue) ([McClure, 2007](#ev-mcclure-aarrr-pirate-metrics-2007-framework)) is a useful lens for internal AI tools that have to win users, not just exist. For developer-productivity use cases, anchor on the **DORA "Four Keys"** (Deployment Frequency, Lead Time for Changes, Change Failure Rate, Time to Restore) ([DORA](#ev-dora-four-keys-framework)) and the **SPACE framework** (Satisfaction, Performance, Activity, Communication, Efficiency) ([Forsgren et al., 2021](#ev-forsgren-space-2021-framework)); **DX Core 4** (Speed, Effectiveness, Quality, Impact) ([DX, 2024](#ev-dx-core-4-2024-framework)) consolidates these into a smaller executive-facing set.

Currently only 48% of organizations use specific KPIs to evaluate gen-AI performance ([Deloitte, 2024](#ev-deloitte-state-genai-2024-specific-kpis)) — defining them per use case is the differentiator, not an afterthought.

## Step 2 — Build the Metric Stack (What to Instrument)

A good measurement system is layered. Technical metrics tell you the system *works*; adoption metrics tell you people *use* it; outcome metrics tell you it *matters*. You need all three, and they answer different questions for different audiences.

| Layer | What it answers | Example metrics |
|---|---|---|
| Technical / operational | Does it work — fast, cheap, and correctly? | Latency, cost per request, error/failure rate, groundedness (the leading hallucination indicator) |
| Adoption & usage | Are people actually using it? | Active users (DAU/MAU), stickiness (DAU ÷ MAU), acceptance rate, retention |
| Outcome / business | Does it create value? | Time saved, output quality, cost reduction, revenue impact |

A concrete "what to instrument" checklist for a new use case:

- [ ] **Technical:** per-request latency (p50/p95), cost per request and per active user, error rate, and groundedness scores on a sampled set of responses.
- [ ] **Adoption:** active users (daily and monthly), stickiness as DAU ÷ MAU, week-over-week retention, and — for assistive tools — **acceptance rate**. A useful real-world anchor: in an enterprise study, developers accepted roughly 30% of Copilot's suggestions, and about 88% of the characters in accepted suggestions were retained ([GitHub & Accenture, 2024](#ev-github-accenture-copilot-2024-acceptance-retention)). Acceptance rate without a retention measure can flatter you.
- [ ] **Outcome:** the pre-AI baseline from "Before You Start," re-measured on the same workflow — time saved, quality (error rate, rework, CSAT), and the dollar translation. For reference on raw task speedup, a controlled experiment found developers using Copilot completed a task 55% faster ([GitHub, 2022, later formalized as Peng et al., 2023](#ev-peng-copilot-rct-2023-speedup)) — but treat lab speedups as hypotheses to validate in your own context, not as your number.

Quote stickiness as a metric, but do not assert a "good" or "great" DAU/MAU threshold — interpret it relative to the use case and its own trend.

## Step 3 — Build Measurement Infrastructure

Metrics you can't reliably collect are wishes. Standing up the infrastructure has four parts, and it should be planned alongside your [technology architecture framework](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md) so telemetry is a first-class platform concern, not bolted on later.

1. **Telemetry / event logging.** Emit structured events for every interaction: request, response, latency, cost, user, acceptance/rejection, and outcome where observable. Standardize the event schema across use cases so you can compare them.
2. **Data pipeline.** Land raw events in a warehouse, transform them into metric tables, and version the definitions. A metric that means three different things in three dashboards is worse than no metric.
3. **LLM observability — tracing + eval layers.** Tracing captures the full chain of a request (prompts, retrieved context, tool calls, model output) so you can debug *why* a response was bad, not just *that* it was. The eval layer scores quality continuously — including **LLM-as-judge evals**, where a strong model grades outputs against a rubric (groundedness, relevance, safety) at a scale human review can't match. Sample human review on top to keep the judge honest.
4. **Dashboards.** One layered view per use case — technical, adoption, outcome — plus a portfolio roll-up. Make the north-star metric and its 3–5 inputs the top of every use-case dashboard.

Build this so the adoption signals feed directly into your [AI adoption framework](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) work — the same usage and retention data that proves value also tells you where adoption is stalling.

## Step 4 — Set a Reporting Cadence

Measurement only changes behavior if it's reviewed on a rhythm, and different audiences need different altitudes and frequencies. Three nested cadences cover it:

- **Weekly — team metric review.** The use-case team looks at the north star and its input metrics plus the technical layer (latency, cost, error, groundedness). Audience: the squad. Purpose: catch regressions and steer the week. Lightweight, operational, no slides.
- **Monthly — business review / steering group.** Product, sponsor, and finance look at adoption and outcome metrics across use cases, with the dollar translation. Audience: program leadership. Purpose: confirm value is materializing and surface use cases that need intervention. This is where the CFO-grade view lives — and where most programs are weak, since only 16% produce regular reports on value created ([Deloitte, 2024](#ev-deloitte-state-genai-2024-cfo-reports)).
- **Quarterly — roadmap & OKR grading.** Leadership grades objectives, reviews the full portfolio, and makes scale/kill/iterate decisions. Audience: executives and the steering committee. Purpose: reallocate budget and set the next quarter's bets.

Keep the metric definitions identical across all three so a number doesn't change meaning as it climbs the org chart. As you mature, use the [measurement maturity scoring](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/05-assessment-measurement-maturity-scoring.md) assessment to track whether your cadence and instrumentation are actually improving.

## Step 5 — Use Measurement to Drive Roadmap Decisions

Measurement that doesn't change the roadmap is theater. The quarterly review (Step 4) is where the data turns into decisions, using explicit gates — **kill, scale, or iterate.**

- **Stage-Gate decision gates** — at each stage, force a **Go / Kill / Hold / Recycle** decision rather than letting projects drift forward by default ([Cooper, Stage-Gate](#ev-cooper-stage-gate-framework)). Every use case past proof-of-concept should face a gate where "keep going" has to be earned against its metrics, not assumed.
- **Build–Measure–Learn and "pivot or persevere"** — Eric Ries's loop, with innovation accounting, frames each use case as an experiment: ship the smallest viable version, measure against the success metrics from Step 1, and decide explicitly whether to pivot (change the approach) or persevere (scale the current one) ([Ries, 2011](#ev-ries-lean-startup-2011-build-measure-learn)). The input metrics are your validated-learning signals.
- **Reward killing weak projects.** The hardest part is cultural: teams cling to projects that the data says should end. Google X explicitly celebrates killing projects — teams are bonused for ending efforts that should end ([Teller, 2016](#ev-teller-google-x-2016-celebrate-killing)). Borrow the norm. A program that never kills anything isn't disciplined; it's just slow to fail.

Tie these gates back to the workflows you're changing via the [workflow optimization framework](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md), so a "scale" decision lands on a concrete process and a "kill" decision frees its resources for the next bet. Given that at least 30% of gen-AI projects are projected to be abandoned after proof of concept ([Gartner, 2024](#ev-gartner-genai-poc-2024-abandonment)), the goal isn't zero kills — it's killing fast and cheap, on evidence, before the spend compounds.

## Key Takeaways

- **Instrument before you deploy.** The baseline you skip is the proof you'll never have — fewer than one in five organizations track well-defined gen-AI KPIs, and that tracking is among the practices most tied to impact ([McKinsey, 2025](#ev-mckinsey-rewiring-2025-kpi-tracking)).
- **Define metrics per use case, not per program.** Use Goals–Signals–Metrics ([Google, 2010](#ev-google-gsm-heart-2010-framework)) to derive one north star plus 3–5 input metrics ([Amplitude, 2024](#ev-amplitude-north-star-metric-framework)); only 48% of organizations use specific gen-AI KPIs today ([Deloitte, 2024](#ev-deloitte-state-genai-2024-specific-kpis)).
- **Measure in three layers** — technical (latency, cost, error, groundedness), adoption (active users, stickiness, acceptance rate, retention), and outcome (time saved, quality, cost, revenue). One layer alone misleads.
- **Build real infrastructure:** standardized telemetry, a versioned pipeline, LLM observability with tracing and eval layers (including LLM-as-judge), and layered dashboards.
- **Run a nested cadence** — weekly team review, monthly business/steering review, quarterly roadmap and OKR grading — with identical metric definitions at every altitude.
- **Let measurement drive the roadmap.** Use Stage-Gate Go/Kill/Hold gates ([Cooper, Stage-Gate](#ev-cooper-stage-gate-framework)) and Build–Measure–Learn pivot-or-persevere decisions ([Ries, 2011](#ev-ries-lean-startup-2011-build-measure-learn)), and reward killing weak projects on evidence rather than defending them.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **McKinsey — *The State of AI: How Organizations Are Rewiring to Capture Value*, 2025.** Less than one in five organizations are tracking KPIs for gen AI solutions — and tracking well-defined KPIs is the practice with the most impact on the bottom line. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-how-organizations-are-rewiring-to-capture-value){#ev-mckinsey-rewiring-2025-kpi-tracking} · verified 2026-06-20 · primary
- **IBM — *IBM Study: More Companies Turning to Open-Source AI Tools to Unlock ROI*, 2024.** Nearly half (47%) of surveyed companies say they are achieving positive ROI from their AI projects. [View source](https://newsroom.ibm.com/2024-12-19-IBM-Study-More-Companies-Turning-to-Open-Source-AI-Tools-to-Unlock-ROI){#ev-ibm-ai-roi-2024-positive-roi} · verified 2026-06-20 · primary
- **BCG — *Where's the Value in AI?*, 2024.** Only 26% of companies have developed the necessary set of capabilities to move beyond proofs of concept and generate tangible value (4% cutting-edge plus 22% advanced). [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-value-2024-beyond-poc} · verified 2026-06-20 · primary
- **Gartner — *Gartner Predicts 30% of Generative AI Projects Will Be Abandoned After Proof of Concept By End of 2025*, 2024.** At least 30% of generative AI projects will be abandoned after proof of concept by the end of 2025, due to poor data quality, inadequate risk controls, escalating costs or unclear business value. [View source](https://www.gartner.com/en/newsroom/press-releases/2024-07-29-gartner-predicts-30-percent-of-generative-ai-projects-will-be-abandoned-after-proof-of-concept-by-end-of-2025){#ev-gartner-genai-poc-2024-abandonment} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** 41% have struggled to define and measure the exact impacts of their GenAI efforts. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-measure-impacts-struggle} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** Only 16% have produced regular reports for the CFO about the value being created with GenAI. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-cfo-reports} · verified 2026-06-20 · primary
- **Google (Rodden, Hutchinson, Fu) — *Measuring the User Experience on a Large Scale (CHI 2010)*, 2010.** The HEART framework (Happiness, Engagement, Adoption, Retention, Task success) with the companion Goals-Signals-Metrics process, from Measuring the User Experience on a Large Scale (CHI 2010). [View source](https://research.google/pubs/measuring-the-user-experience-on-a-large-scale-user-centered-metrics-for-web-applications/){#ev-google-gsm-heart-2010-framework} · verified 2026-06-20 · primary
- **Amplitude — *The North Star Playbook*, 2024.** The North Star Framework connects a single North Star Metric to a set of typically three to five input metrics that teams can directly influence. [View source](https://amplitude.com/books/north-star/about-north-star-framework){#ev-amplitude-north-star-metric-framework} · verified 2026-06-20 · primary
- **Dave McClure (500 Startups) — *Startup Metrics for Pirates: AARRR!*, 2007.** Startup Metrics for Pirates frames the five metrics that matter as Acquisition, Activation, Retention, Referral, and Revenue (AARRR). [View source](https://500hats.typepad.com/500blogs/2007/09/startup-metrics.html){#ev-mcclure-aarrr-pirate-metrics-2007-framework} · verified 2026-06-20 · primary
- **DORA / Google Cloud — *DORA software delivery performance metrics (Four Keys)*, 2024.** DORA identifies four key metrics of software delivery performance: Deployment Frequency and Lead Time for Changes (throughput), and Change Failure Rate and Time to Restore Service (stability). [View source](https://dora.dev/guides/dora-metrics-four-keys/){#ev-dora-four-keys-framework} · verified 2026-06-20 · primary
- **Forsgren et al. — *The SPACE of Developer Productivity (ACM Queue 19(1))*, 2021.** The SPACE of Developer Productivity defines five dimensions: Satisfaction and well-being, Performance, Activity, Communication and collaboration, and Efficiency and flow. [View source](https://queue.acm.org/detail.cfm?id=3454124){#ev-forsgren-space-2021-framework} · verified 2026-06-20 · primary
- **DX — *Introducing the DX Core 4*, 2024.** The DX Core 4 organizes developer productivity into four dimensions (Speed, Effectiveness, Quality, Impact), encapsulating the DORA, SPACE, and DevEx frameworks. [View source](https://newsletter.getdx.com/p/introducing-the-dx-core-4){#ev-dx-core-4-2024-framework} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** Organizations are using specific KPIs for evaluating GenAI performance (48%). [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-specific-kpis} · verified 2026-06-20 · primary
- **GitHub & Accenture — *Research: Quantifying GitHub Copilot's impact in the enterprise with Accenture*, 2024.** In our study developers accepted around 30% of GitHub Copilot's suggestions, and retained 88% of GitHub Copilot-generated characters in their editor. [View source](https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-in-the-enterprise-with-accenture/){#ev-github-accenture-copilot-2024-acceptance-retention} · verified 2026-06-20 · primary
- **Peng et al. — *The Impact of AI on Developer Productivity: Evidence from GitHub Copilot*, 2023.** The treatment group with access to the AI pair programmer completed the task 55.8% faster than the control group; developers with GitHub Copilot took on average 1 hour 11 minutes versus 2 hours 41 minutes, across 95 professional programmers. [View source](https://arxiv.org/abs/2302.06590){#ev-peng-copilot-rct-2023-speedup} · verified 2026-06-20 · primary
- **Robert G. Cooper / Stage-Gate International — *The Stage-Gate Idea-to-Launch System*.** The Stage-Gate system separates stages by gates, where each gate yields one of four decisions: Go, Kill, Hold, or Recycle. [View source](https://www.stage-gate.com/blog/the-stage-gate-model-an-overview/){#ev-cooper-stage-gate-framework} · verified 2026-06-20 · primary
- **Eric Ries — *The Lean Startup*, 2011.** The Lean Startup names Build-Measure-Learn as the core feedback loop, with innovation accounting to measure progress and a pivot-or-persevere decision. [View source](https://theleanstartup.com/book){#ev-ries-lean-startup-2011-build-measure-learn} · verified 2026-06-20 · primary
- **Astro Teller (X / Google X), TED — *The unexpected benefit of celebrating failure (TED)*, 2016.** At X, teams kill their own ideas once the evidence is in because they are rewarded for it with applause, promotions, and bonuses for every member of teams that ended their projects. [View source](https://www.ted.com/talks/astro_teller_the_unexpected_benefit_of_celebrating_failure){#ev-teller-google-x-2016-celebrate-killing} · verified 2026-06-20 · primary
