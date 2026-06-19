---
type: Playbook
title: Integrated Assessment
description: The full eight-dimension diagnostic that produces a prioritized gap list across all tracks.
tags: [program-management, assessment, diagnostic, playbook]
timestamp: "2026-06-19"
---

Most AI programs are funded one track at a time — whichever function shouted loudest — and then stall for reasons that live in a track nobody scored. The Integrated Assessment exists to stop that. It is a single cross-functional working session that scores all eight tracks on one shared ladder, lays the results side by side, and produces a *prioritized gap list*: not "here is everything wrong," but "here is the one constraint to relieve next." It is the operational front door to [Running the Program](/enterprise-ai-transformation/running-the-program/program-architecture.md) — you run it before you sequence, and again on a cadence to see whether the constraint has moved.

This page is the *how-to-run-it* companion to the [Framework Architecture](/enterprise-ai-transformation/framework-architecture.md), which already defines the eight tracks, their dependencies, the two failure modes, and the full maturity matrix. This page does not re-print that matrix; it tells you how to source a score for each track, read the pattern, and turn it into an investment case. The need is real: only **13% of organizations are "fully ready" to deploy and leverage AI — down from 14% the year before** *(Cisco, 2024)*, only **1% of leaders describe their AI deployment as "mature"** *(McKinsey, 2025)*, and **at least 30% of gen-AI projects are projected to be abandoned after proof of concept by the end of 2025** — for reasons Gartner lists as poor data quality, inadequate risk controls, escalating costs, and unclear business value *(Gartner, 2024)*. Every one of those failure modes lives in a *different* track. A single-track view cannot see them; an integrated one can.

---

## What This Is For

The Integrated Assessment answers one question: **given everything in motion, where is value actually being throttled, and what should we fund next?** It is deliberately a cross-functional *session*, not a survey emailed to eight owners, because the most expensive AI gaps are organizational, not technical. BCG's guidance is to direct roughly **70% of AI effort and resources to people and process, 20% to technology and data, and 10% to algorithms** *(BCG, 2024)* — and you only find people-and-process gaps when the people who own them are in the same room reconciling their scores against each other.

Use it three ways:

- **At program start** — to set the baseline and the first sequence (feeds [Sequencing Playbooks](/enterprise-ai-transformation/running-the-program/sequencing-playbooks.md) and [The 90-Day Launch](/enterprise-ai-transformation/running-the-program/the-90-day-launch.md)).
- **On a cadence** — quarterly or per planning cycle, to confirm the binding constraint has moved and to re-prioritize. Organizations that keep AI on a recurring governance rhythm pull ahead: **63% of high-AI-ROI organizations discuss AI at every board meeting, versus only 13% of low-ROI organizations** *(Protiviti, 2026)*.
- **Before a major investment decision** — to check that the spend targets the actual constraint, not the most visible layer.

---

## The Eight Dimensions Are the Eight Tracks

The diagnostic has exactly eight dimensions because the framework has exactly eight tracks. There is no separate instrument to maintain: each track owns a detailed assessment, and the Integrated Assessment is the *roll-up* that places those eight scores on one comparable scale. In the session you do not re-derive each score from scratch — you pull it from the track's own assessment page, or run that assessment if it has never been scored.

| # | Dimension (Track) | What you are scoring | Source assessment |
| --- | --- | --- | --- |
| 01 | AI Strategy & Leadership | Is there a funded, business-anchored set of AI priorities every other track is scoped against? | [Strategic Readiness Scoring](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/05-assessment-strategic-readiness-scoring.md) |
| 02 | AI Governance & Risk | Do guardrails — acceptable use, model risk, compliance — exist and gate real work? | [Governance Maturity Scoring](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/05-assessment-governance-maturity-scoring.md) |
| 03 | Data Readiness | Is the data AI depends on trustworthy, governed, and accessible to use cases? | [AI Readiness Assessment Framework](/enterprise-ai-transformation/tracks/03-data-readiness/04-assessment-and-measurement/ai-readiness-assessment-framework.md) |
| 04 | Technology Architecture & Platform | Is there a coherent platform with standard model access and patterns, not point-solution sprawl? | [Platform Maturity Scoring](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/05-assessment-platform-maturity-scoring.md) |
| 05 | Workflow Optimization & Automation | Are end-to-end workflows actually being redesigned with AI, not just personal assistance? | [Workflow Maturity & Opportunity Scoring](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/06-assessment-workflow-maturity-and-opportunity-scoring.md) |
| 06 | AI Adoption & Culture | Do target teams use AI in daily work, with real behavior change rather than shelfware? | [Adoption Maturity Scoring](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/04-assessment-adoption-maturity-scoring.md) |
| 07 | Talent & Capability Building | Does the organization have — and keep building — the competencies the work requires? | [Talent Readiness Scoring](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/05-assessment-talent-readiness-scoring.md) |
| 08 | Measurement & Value Realization | Can you tie AI to value, prove it to finance, and let evidence reprioritize spend? | [Measurement Maturity Scoring](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/05-assessment-measurement-maturity-scoring.md) |

The eight group into four layers — **Direction** (01, 02), **Foundation** (03, 04), **Execution** (05, 06, 07), and **Feedback** (08) — which is the lens you use later to read the pattern. Each track's assessment uses its own dimensions internally (Measurement, for example, scores five sub-dimensions); the Integrated Assessment consumes only the *headline level* each produces.

---

## Scoring Methodology

Every track is scored on the same five-level ladder defined in the [Framework Architecture](/enterprise-ai-transformation/framework-architecture.md), so the eight scores are directly comparable:

**1 Nascent · 2 Developing · 3 Emerging · 4 Scaling · 5 Transformational**

Two rules make the scores honest:

1. **Score on evidence, not intent.** The level is what is *demonstrably true today* — backed by an artifact a skeptic would accept (a funded plan, a deployed control, a production workflow, a finance-reviewed value number) — never what is planned, budgeted, or "almost done." A roadmap to redesign workflows is not a redesigned workflow. This is the single most common way an assessment lies to its sponsor.
2. **Source each score from the track's own assessment, then reconcile in the room.** Each owner brings their track's score *with its evidence*. The session's job is to challenge it: a Strategy owner claiming Level 4 while no other track can name the three funded priorities is really at Level 2. The cross-functional table is the calibration mechanism — it catches the optimism that a self-scored survey never would.

Record one level per track plus a one-line evidence note. The output is a profile of eight numbers, not an average — averaging is the cardinal error, because it hides exactly the low score that is throttling everything else.

---

## Reading the Pattern: Finding the Binding Constraint

A completed profile is read for *shape*, not sum. The whole point of scoring all eight at once is to see which one is gating the rest.

> **The binding-constraint principle:** a track is only as effective as its weakest upstream dependency. Funding Workflow (05) on top of unready Data (03) produces motion without value; rolling out tools (06) without Talent (07) produces logins without usage. Find the lowest track that is throttling the ones downstream of it — and fund *that*, not the most visible or fashionable layer.

Three patterns to look for, drawn from the [Framework Architecture](/enterprise-ai-transformation/framework-architecture.md):

- **Spiky (a 4 next to a 1).** A high track is being throttled by a low neighbor. This is the binding constraint made visible. The `03 → 04` (Data → Platform) and `05 → 06/07` (Workflow → Adoption/Talent) boundaries are where programs most often stall — "working pilots that won't scale" almost always trace to a Level-1 dependency next door. Each of the three classic constraints has its own evidence: data quality and availability is the **top-cited AI adoption barrier at 52%** *(PEX Network, 2025)*; **63% of employers name skills gaps the biggest barrier to transformation** through 2030 *(World Economic Forum, 2025)*; and **regulatory compliance is the #1 barrier to deploying gen-AI, cited by 38%, up from 28% a year earlier** *(Deloitte, 2025)*. Whichever is your lowest score is your constraint.
- **Flat-but-low (everything at 2).** No track has crossed the threshold where value appears — the modal organization. The fix is *not* to nudge all eight up a notch. Pick one or two tracks on the critical path and push them to Level 3–4 so something crosses into value, then re-assess.
- **Foundation gap under execution pressure.** High Direction and Execution scores sitting on Level-1/2 Foundation (Data, Platform) is the "boil the ocean" failure pre-loaded — execution work is being built on substrate that will force a redo. Relieve Foundation before pouring more into Execution.

The constraint you name here is the input to [Sequencing Playbooks](/enterprise-ai-transformation/running-the-program/sequencing-playbooks.md): sequence by dependency, not by track number.

---

## Framing the Investment Case

A prioritized gap list is only useful if it changes where money goes. Convert the profile into a case in three moves, anchored to [Track 08 — Measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md):

1. **Name the constraint and its downstream cost.** "Data Readiness at Level 2 is capping three Level-4 workflow pilots that cannot scale." That sentence — constraint, level, and the higher-scoring work it throttles — is the case. It reframes the ask from "fund Data" to "unlock the value already half-built on top of it."
2. **Size the prize against the leader–laggard gap.** The reason to relieve the constraint is the value differential it unlocks. BCG's "future-built" leaders — just **5% of organizations** — report roughly **1.7x the revenue growth, 1.6x higher EBIT margins, and 40% greater cost savings than laggards** *(BCG, 2025)*, and only about **6% of organizations are AI high performers attributing more than 5% of EBIT to AI** *(McKinsey, 2025)*. The gap between the profile you have and the one those firms have is the size of the opportunity.
3. **Commit to measuring the unlock.** Tie the investment to a Track 08 metric and a re-assessment date, so the next session can show the constraint moved. This is what separates leaders: **more than a third of gen-AI high performers have clear ways to measure and track the value of their gen-AI work, versus only about one in ten of other organizations** *(McKinsey, 2024)*. Without the measurement commitment, the gap list becomes a wish list.

---

## Run It in 90 Minutes

One session, one room (or one call), all eight track owners plus the program sponsor. Pre-work: each owner brings their track's current score *with evidence*.

| Time | Activity |
| --- | --- |
| 0–10 min | **Frame.** Sponsor restates the question — *where is value being throttled, and what do we fund next?* Reaffirm: score on evidence, not intent. |
| 10–45 min | **Score the eight tracks.** Each owner presents their level and its evidence (~4 min each). The room challenges and calibrates; record one level + a one-line note per track. |
| 45–60 min | **Plot the profile.** Lay the eight numbers in track order. Mark the layers (Direction / Foundation / Execution / Feedback). Look for spiky, flat-but-low, and foundation-gap patterns. |
| 60–75 min | **Name the binding constraint.** Agree the single lowest track throttling downstream work. Resist the urge to fix everything — name *one* (at most two). |
| 75–90 min | **Frame the case + commit.** State constraint → downstream cost → the unlock. Assign an owner, a first move (hand off to [Sequencing Playbooks](/enterprise-ai-transformation/running-the-program/sequencing-playbooks.md)), a Track 08 metric, and the re-assessment date. |

Keep it to 90 minutes by timeboxing ruthlessly: the deep work already happened inside each track's own assessment. This session reconciles and prioritizes — it does not re-derive.

---

## Key Takeaways

- **One session, one ladder, eight tracks.** The Integrated Assessment scores all eight tracks on the shared **1 Nascent · 2 Developing · 3 Emerging · 4 Scaling · 5 Transformational** ladder and produces a prioritized gap list — not a to-do list.
- **The eight dimensions are the eight tracks, 1:1.** Source each score from the track's own assessment page; the session reconciles and rolls up, it does not re-derive.
- **Score on evidence, not intent, and never average.** A profile of eight numbers tells the truth; a mean hides the low score that is throttling everything. Only **1% of leaders call their AI deployment mature** *(McKinsey, 2025)* — optimism is the default failure.
- **Read the shape to find the binding constraint.** Spiky (4-next-to-1), flat-but-low, and foundation-gap patterns each point to the one track to fund next — usually data, talent, or governance, the three most-cited blockers *(PEX Network, 2025; WEF, 2025; Deloitte, 2025)*.
- **Convert the constraint into an investment case and commit to measuring the unlock.** Tie it to a Track 08 metric and a re-assessment date — high performers are several times more likely than others to have clear ways to measure gen-AI value *(McKinsey, 2024)*, and they run AI on a recurring cadence *(Protiviti, 2026)*.
