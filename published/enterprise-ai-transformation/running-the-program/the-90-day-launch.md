---
type: Playbook
title: The 90-Day Launch
description: "What to do in the first 90 days of an AI transformation program regardless of org type, week by week."
tags: [program-management, launch, 90-day-plan, playbook]
timestamp: "2026-06-19"
---

The first 90 days set the trajectory of an AI program more than any other quarter. Get them right and you have a sponsor, a baseline, a shipped use case, and evidence that pulls the next investment. Get them wrong and you have a strategy deck, a long backlog, and an executive whose patience is already spent — the most common way programs die. At least 30% of gen-AI projects are projected to be abandoned after proof of concept by the end of 2025, driven by poor data quality, weak controls, escalating cost, and unclear value *(Gartner, 2024)*, and only 26% of companies have built the capabilities to move beyond proofs of concept and generate tangible value *(BCG, 2024)*. The 90-day launch exists to put your program in that minority — not by going faster, but by sequencing the right moves and proving value before you scale.

This playbook is org-type-agnostic: it works whether you are a regulated enterprise or a digitally native team. *Which* track you pour intensity into first is org-specific — that ordering lives in the [sequencing playbooks](/enterprise-ai-transformation/running-the-program/sequencing-playbooks.md). What follows is the launch sequence that holds regardless of where your binding constraint sits, grounded in the [framework architecture](/enterprise-ai-transformation/framework-architecture.md) and run through the [program architecture](/enterprise-ai-transformation/running-the-program/program-architecture.md).

> **The throughline: instrument measurement before you deploy, and let early evidence pull the next investment.** A baseline you skip is proof you will never have — fewer than one in five organizations track well-defined KPIs for their gen-AI solutions, and KPI tracking is among the practices most correlated with bottom-line impact *(McKinsey, 2025)*. Everything in the first 90 days bends toward shipping one measured thing, not many unmeasured ones.

## The 90-day plan at a glance

| Phase | Weeks | Focus | What exists at the end |
| --- | --- | --- | --- |
| 1. Assessment & alignment | 1–2 | Name the sponsor, run the integrated assessment, pick the binding constraint, set success metrics up front | A funded mandate, an agreed constraint, and metrics defined *before* any tool ships |
| 2. Quick wins & foundation | 3–6 | Lightweight governance guardrails, instrument measurement from day one, pick 1–2 quick-win use cases | Guardrails live, telemetry in place, baselines captured, use cases scoped |
| 3. First use case activation | 7–12 | Ship to real users, measure against baseline, prepare the first reprioritization | A deployed use case with measured value and an evidence-based next bet |

The phases stagger intensity rather than running as a waterfall: governance and measurement begin in Phase 1 as lightweight activity and deepen as the work demands it. This is the framework's core operating rule — run the tracks concurrently but at staggered intensity, and let Measurement (08) pace the next investment.

## Weeks 1–2 — Assessment and alignment

The launch begins with people and direction, not technology. Three things must be true before week 2 ends.

**Name the executive sponsor — and make the role active, not nominal.** Sponsorship is consistently the single largest predictor of change-program success: across all twelve of Prosci's longitudinal studies, active and visible sponsorship was the number-one contributor to success *(Prosci, 2016)*, and PMI found that when more than 80% of projects have active executive-sponsor support, 65% more of them succeed *(PMI, 2016)*. In AI specifically, a CEO's oversight of AI governance is the element most correlated with higher bottom-line impact from gen AI, especially at larger companies *(McKinsey, 2025)*. A sponsor who lends a name but not time is the same as no sponsor. Define what the role costs them: a recurring review, budget authority, and air cover when the first reprioritization kills something.

**Run the integrated assessment.** Score all eight tracks on the same maturity ladder to see the whole board at once, using the [integrated assessment](/enterprise-ai-transformation/running-the-program/integrated-assessment.md). The output is not a grade — it is the location of your binding constraint.

**Pick the binding constraint and set success metrics up front.** A track is only as effective as its weakest upstream dependency; funding the most visible layer instead of the constraining one produces motion without value. Name the one or two tracks you will push, and — critically — define what success looks like *before* anything ships. Use Goals–Signals–Metrics to derive one north-star metric and 3–5 input metrics per intended use case (see the [measurement framework](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md)). Deciding what to measure now, while there is nothing yet to measure, is the discipline that separates programs that prove value from the 41% who later struggle to define and measure gen-AI's impact at all *(Deloitte, 2024)*.

## Weeks 3–6 — Quick wins and foundation setting

Phase 2 turns the mandate into running infrastructure and scoped work. The order matters: guardrails and telemetry come before, not after, the use case.

**Stand up lightweight governance guardrails.** You do not need a complete policy library to start — you need an acceptable-use boundary and a review path for new use cases, so the first deployment happens inside known limits rather than around them. Keep it proportionate to risk and expand it as use cases demand; the full picture lives in [AI Governance & Risk](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/index.md). Regulated organizations will weight this more heavily and earlier — see the sequencing playbooks for that adjustment.

**Instrument measurement from day one.** This is the non-negotiable. Before a single user touches the system, stand up event logging (request, response, latency, cost, acceptance, outcome) and capture the pre-AI baseline — cycle time, cost per task, error rate, volume — for the exact workflow you are about to change. The most expensive mistake in AI measurement is reconstructing a baseline after the fact: once the tool is live, the "before" state is gone and every later number is an estimate you will spend months defending. The [practitioner guide to standing up measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/04-practitioner-guide-standing-up-ai-measurement.md) walks through the instrumentation step by step.

**Pick 1–2 quick-win use cases.** Resist the urge to launch a portfolio. Short-term wins are not a nicety — in change research they are what sustains momentum and proves the effort is working; running a long change effort with no attention to early, visible wins is extremely risky *(Kotter, 1996)*. Choose use cases that are visible, unambiguously attributable to the AI, and clearly tied to the constraint you named. One or two, instrumented and baselined, beat ten that ship unmeasured.

## Weeks 7–12 — First use case activation

Now you ship — but shipping is the start of measurement, not the finish line.

**Ship to real users.** Put the use case in the hands of the people whose work it changes, inside the guardrails from Phase 2. Real users surface the gap between a demo that works and a workflow that holds; this is where pilots that looked promising either stick or reveal they never had product-market fit internally.

**Measure against the baseline.** Re-measure the same workflow on the same metrics you captured before deployment — time saved, quality, cost — alongside adoption signals (active users, acceptance rate, retention) and technical health (latency, cost, error rate). Adoption without outcome is logins, not value; this layered read is what tells you whether the use case actually moved the constraint. The contrast you are trying to avoid is stark: only 47% of IT decision-makers say their company is currently achieving positive ROI from its AI projects *(IBM, 2024)*, and only 48% of organizations even use specific KPIs to evaluate gen-AI performance *(Deloitte, 2024)*. Your instrumented baseline is what puts you on the right side of those numbers.

**Prepare the first reprioritization.** The evidence from weeks 7–12 is the input to your next quarter, not a victory lap. Bring it to the sponsor and make an explicit decision — scale the use case, iterate on it, or kill it — and let that decision pull the next investment. This closes the loop: Measurement (08) feeds back into Strategy (01), and the constraint you relieve next is the one the evidence points to, not the one that was loudest in week 1.

## Creating momentum without over-promising

The failure mode that ends programs is not slow progress — it is a gap between what leadership was promised and what the data shows. Generative AI has slid into the trough of disillusionment precisely because excitement outran realized value, with executives impatient for returns that organizations struggle to prove *(Gartner, 2024)*. The 90-day launch is designed to close that gap, and two disciplines do most of the work.

**Set expectations against evidence, not enthusiasm.** Tell the sponsor in week 1 what the first 90 days will and will not produce: one or two measured use cases, a real baseline, and an evidence-based recommendation — not enterprise-wide transformation. A modest promise you can prove beats an ambitious one you cannot. The sponsor's standing — and your program's funding — survives on the credibility of the numbers you bring back.

**Instrument before you deploy — because that is what makes the evidence real.** Every claim of value in the reprioritization rests on a comparison to a baseline you can only capture before the tool goes live. Skip it and your "win" is an anecdote that erodes the moment finance asks how you know. Capture it and even a kill decision is a credible, defensible result that frees resources for the next bet. Instrumenting first is not measurement overhead; it is the thing that lets early evidence pull the next investment instead of executive patience pushing it off a cliff.

## Key Takeaways

- **The first 90 days set the trajectory.** Aim for one or two *measured* use cases, not many unmeasured ones — only 26% of companies have moved beyond proofs of concept to tangible value *(BCG, 2024)*, and at least 30% of gen-AI projects are projected to be abandoned after PoC *(Gartner, 2024)*.
- **Weeks 1–2: name an active sponsor, assess all eight tracks, pick the binding constraint, and define success metrics before anything ships.** Active sponsorship is the #1 predictor of change success *(Prosci, 2016; PMI, 2016)*, and CEO oversight of AI governance is the element most correlated with bottom-line impact *(McKinsey, 2025)*.
- **Weeks 3–6: lightweight guardrails, day-one instrumentation, and 1–2 quick wins.** Capture the baseline before the tool is live — it cannot be recreated later — and pick wins that are visible and attributable *(Kotter, 1996)*.
- **Weeks 7–12: ship to real users, measure against the baseline, and prepare the first reprioritization.** Read value in three layers; adoption without outcome is logins, not value. Only 47% of organizations report positive AI ROI today *(IBM, 2024)*.
- **Create momentum without over-promising.** Gen AI is in the trough of disillusionment because hype outran proof *(Gartner, 2024)* — promise what you can measure, and let early evidence, not executive impatience, pace the next investment.
