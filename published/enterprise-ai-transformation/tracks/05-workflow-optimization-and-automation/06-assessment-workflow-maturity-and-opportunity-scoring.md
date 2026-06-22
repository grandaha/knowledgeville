---
type: Playbook
title: "Assessment: Workflow Maturity & Opportunity Scoring"
description: "Score workflow maturity across six dimensions, size automation opportunities, and prioritize them on a value × data readiness × complexity matrix to produce a sequenced roadmap."
tags: [workflow-optimization, assessment, prioritization, maturity, data-readiness]
timestamp: "2026-06-17"
---

## What This Is For

This assessment does one thing: it turns a vague backlog of "things we could automate" into a **ranked, evidence-backed list of workflow opportunities** — each one scored for how mature the surrounding function is, how much value it would release, how ready its data is, and how hard it would actually be to build. The output is a sequencing decision: what to do first, what to stage, and what to leave alone until the foundations exist.

It is deliberately not a vanity scorecard. It does not produce a single "automation readiness" grade to present upward. It produces a prioritized opportunity list that changes what gets funded in the next two quarters. If the result does not reorder your roadmap, you ran it wrong.

It is the diagnostic companion to the [workflow optimization framework](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md) and feeds directly into the [practitioner guide for running a workflow optimization program](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/05-practitioner-guide-running-a-workflow-optimization-program.md). The maturity rubric below assumes familiarity with [the four levels of workflow–AI integration](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md), which describe *how deeply* AI is embedded in a workflow; this assessment scores *whether a given workflow is ready* for that integration and *whether it is worth the effort*.

Distinguish it from two adjacent assessments. It is **not** a data readiness audit — that is [Track 03](/enterprise-ai-transformation/tracks/03-data-readiness/index.md), and this assessment treats data readiness as one input to scoring an opportunity, not the whole picture. And it is **not** a value-realization measurement exercise — that is [Track 08](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md), which measures outcomes after you have built something. This assessment runs *before* you build, to decide what to build.

Run it when: a function has accumulated more automation ideas than it can fund; leadership is pushing a flashy use case and you need to test it against the alternatives; or a wave of pilots has stalled and you need to understand why before launching the next one.

> Across roughly 300 public deployments, an MIT study found that about **95% of enterprise generative-AI pilots delivered little to no measurable impact on profit and loss** — and the root cause was not model quality but the failure to integrate AI into actual workflows ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)).
>
> Organizations seeing the greatest impact from AI are **nearly three times as likely** to say they have fundamentally redesigned workflows as part of their AI efforts ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-workflow-redesign-highperf)).

The lesson behind those two numbers is the entire reason this assessment exists: value comes from picking the *right workflows* and rebuilding them, not from deploying AI on top of whatever process happens to be loudest in the room. The widely cited failure rates of automation programs are, more often than not, prioritization failures — chasing the flashy use case, ignoring data readiness, and underestimating complexity. This assessment is a structured defense against all three.

---

## Part 1: Workflow Maturity Scoring

Before sizing individual opportunities, score the **maturity of the function** the workflow lives in. A brilliant opportunity inside a function that cannot see its own processes, has no measurement, and cannot absorb change will fail no matter how good the idea is. Maturity scoring tells you whether the *ground* is ready.

Score each of six dimensions on a 1–5 scale, independently, on evidence rather than aspiration. The dimensions do not average into a grade so much as describe a shape — and the shape tells you whether to invest in opportunities now or in foundations first.

### Dimension 1: Process Visibility

Whether the organization actually knows how its work flows — the steps, the handoffs, the volumes, the exceptions — or whether the "process" exists only as folklore in the heads of the people who run it. You cannot size or redesign what you cannot see.

| Level | What it looks like |
| --- | --- |
| 1 | No documented processes. How work gets done is tribal knowledge; no one can describe the end-to-end flow or cite volumes. |
| 2 | Some processes are documented in static diagrams or SOPs, but they are out of date and do not reflect how work actually happens. |
| 3 | Key processes are mapped and reasonably current; basic volume and cycle-time data exists but is gathered manually and infrequently. |
| 4 | Core processes are mapped with current volume, cycle-time, and exception data; some processes are observed via system logs or process-mining tooling. |
| 5 | Process visibility is continuous and data-driven; process mining or equivalent instrumentation surfaces bottlenecks, variants, and rework loops in near-real time. |

### Dimension 2: Workflow Standardization

Whether a process runs the same way every time or fragments into dozens of undocumented variants. Automation amplifies whatever it is pointed at: standardize first, or you automate the chaos.

| Level | What it looks like |
| --- | --- |
| 1 | Every person runs the process differently; no agreed standard exists. |
| 2 | A nominal standard exists on paper but is widely ignored; high variant count in practice. |
| 3 | A standard exists and is mostly followed for the common path; exception handling is ad hoc. |
| 4 | The process is standardized with defined exception paths; deviations are tracked and managed. |
| 5 | The process is standardized, instrumented, and continuously refined; variants are deliberate design choices, not drift. |

### Dimension 3: Data Readiness for the Workflow

Whether the specific data this workflow consumes and produces is accessible, structured, and trustworthy enough to drive automated decisions. This is the workflow-scoped slice of the broader [Track 03 data readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md) picture — and it is the single most common reason automation stalls.

| Level | What it looks like |
| --- | --- |
| 1 | The data the workflow needs is scattered, locked in PDFs or email, or does not exist in any retrievable form. |
| 2 | Data exists in systems but is poorly structured, inconsistent, or requires heavy manual cleanup before use. |
| 3 | Core data is accessible via systems or exports; quality is adequate for the common case but has known gaps. |
| 4 | Workflow data is accessible through APIs or a governed store, is structured, and has defined quality and ownership. |
| 5 | Workflow data is real-time, governed, quality-monitored, and already feeding analytics or models reliably. |

### Dimension 4: Automation and AI Capability

Whether the function has the tooling, integration surface, and skills to actually build and operate automated or AI-assisted workflows — or whether every attempt is a one-off prototype that no one can maintain.

| Level | What it looks like |
| --- | --- |
| 1 | No automation tooling and no relevant skills; any automation is manual scripting by one person. |
| 2 | Some point tools (macros, basic RPA) used in isolation; no integration layer; bus-factor of one. |
| 3 | A sanctioned automation or AI toolset exists and is used for a few workflows; integration is possible but bespoke each time. |
| 4 | A platform layer (orchestration, APIs, sanctioned AI tooling — see [the tooling landscape](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/04-tooling-landscape.md)) supports new builds; reusable patterns exist; skills are spread across a team. |
| 5 | Automation and AI capability is a managed platform with reusable components, observability, and a team accountable for its health. |

### Dimension 5: Change and Adoption Readiness

Whether the people who run the workflow will actually adopt a redesigned version — or quietly route around it. Automation that is built but not adopted is the most expensive kind of failure.

| Level | What it looks like |
| --- | --- |
| 1 | Change is resisted by default; past automation attempts were abandoned or worked around. |
| 2 | Change is tolerated when mandated but not supported; no enablement or communication accompanies rollouts. |
| 3 | Change is managed for major initiatives with some training and communication, applied inconsistently. |
| 4 | A repeatable change approach exists — stakeholder involvement, enablement, feedback loops — and is applied to automation rollouts. |
| 5 | The function actively co-designs workflow changes with the people who run them; adoption is measured and reinforced. |

### Dimension 6: Measurement Discipline

Whether the function can establish a baseline and prove (or disprove) the impact of a workflow change. Without it, you cannot size opportunities credibly, and you cannot tell a success from a sunk cost. This dimension is the on-ramp to [Track 08 measurement and value realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md).

| Level | What it looks like |
| --- | --- |
| 1 | No baselines; no one can state current cycle time, cost-per-transaction, or error rate. |
| 2 | Some metrics exist but are inconsistent and not tied to specific workflows. |
| 3 | Key workflows have baseline metrics captured at least periodically; impact is estimated after the fact. |
| 4 | Workflows have defined baselines and target metrics; pre/post impact is measured for changes. |
| 5 | Metrics are instrumented and continuous; impact of every change is tracked against baseline automatically. |

### The Maturity Ladder

Average the six dimensions for a single label — but treat the lowest dimension as the binding constraint, not the mean.

| Level | Name | Where you are |
| --- | --- | --- |
| 1 | Opaque | Work is invisible and unstandardized. You cannot reliably size or redesign anything yet. |
| 2 | Aware | Some documentation and tooling exist, but data, standardization, and measurement are weak. Automation here amplifies chaos. |
| 3 | Capable | Core processes are visible, partly standardized, and measurable. You can pursue selected opportunities — this is where most functions sit and stall. |
| 4 | Optimizing | Processes are standardized, instrumented, data-ready, and supported by a platform and change capability. Opportunities can scale. |
| 5 | Adaptive | Workflows are continuously instrumented, redesigned, and improved; the function selects and ships opportunities as a routine capability. |

Most functions cluster at Level 2–3 and stall at the Level 3→4 gap — they can build individual automations but lack the standardization, data foundation, and measurement to scale them. The Deloitte process-mining survey found that even among process-aware organizations, **automation identification was a stated objective for only 38% of respondents**, while process transparency (51%) and cost savings (59%) ranked higher ([Deloitte, 2025](#ev-deloitte-process-mining-survey-2025-objectives)) — a sign that many functions are still working on *seeing* their processes, a Level 3 capability, before they can systematically *automate* them.

---

## Part 2: Opportunity Identification and Sizing

With maturity understood, inventory candidate workflows and size each one. The goal is a defensible, comparable value estimate — not precision. A consistent method applied across every candidate is worth far more than a sophisticated model applied to one.

### Where opportunities come from

Three reliable sources, in rough order of rigor:

- **Process mining / system logs** — the most objective source. Instrumentation surfaces high-frequency, repetitive, rule-bound steps (routing, approvals, data entry, reconciliation) that are prime candidates. Process mining is well suited to identifying tasks that take roughly two to thirty minutes and recur at volume ([ServiceNow, 2024](#ev-servicenow-process-mining-2024-task-profile)).
- **Frontline interviews** — the people doing the work know where the rework, the swivel-chair copying, and the waiting happen. Necessary, but bias toward the loudest pain, so triangulate against data.
- **Exception and error logs** — high-error, high-cost steps are often the best opportunities because the value is in *quality*, not just time.

### The sizing formula

Estimate the **annual value at stake** for each candidate, then net out the cost to build and run it:

```
Annual gross value =
   (Volume per year)
 × (Time per instance × fully-loaded labor cost)   ← time/cost released
 + (Error rate × cost per error × Volume)           ← error/quality cost avoided
 + (Strategic/throughput upside)                    ← qualitative; size only if defensible

Net annual value = Annual gross value − (build cost amortized + annual run cost)
```

Four levers drive the time-and-cost term — **volume × time × frequency × error cost** — and a candidate has to score well on the *combination*, not one lever. A two-minute task done 200,000 times a year dwarfs a two-hour task done monthly.

### A worked example (illustrative numbers — method demonstration only)

> The figures below are illustrative placeholders to show the arithmetic. They are not sourced facts. Replace every number with your own measured baseline.

Take an invoice-exception handling workflow:

- **Volume:** 60,000 exception cases per year
- **Time per instance:** 12 minutes of analyst handling
- **Fully-loaded labor cost:** $55 per hour → $11 per case  <!-- noev: worked-example / rubric figure, not a sourced claim -->
- **Error rate today:** 4% of cases mishandled  <!-- noev: worked-example / rubric figure, not a sourced claim -->
- **Cost per error:** $400 (rework + late-payment penalty), so $960,000/yr in error cost on the 2,400 mishandled cases  <!-- noev: worked-example / rubric figure, not a sourced claim -->

Time/cost released (assume automation handles 70% of cases end-to-end):  <!-- noev: worked-example / rubric figure, not a sourced claim -->

```
60,000 × 70% × (12/60 hr) × $55 = 60,000 × 0.70 × 0.2 × $55 = $462,000/yr
```

Error cost avoided (assume error rate falls from 4% to 1%):  <!-- noev: worked-example / rubric figure, not a sourced claim -->

```
(4% − 1%) × 60,000 × $400 = 0.03 × 60,000 × $400 = $720,000/yr
```

Gross annual value ≈ **$1.18M**. Subtract an amortized build cost of, say, $250,000 over two years ($125K/yr) plus $90K/yr run cost → **net ≈ $965K/yr**. This single number is what enters the prioritization matrix below. Crucially, in this illustrative case more than half the value came from *error reduction*, not time savings — which is exactly why sizing on time alone systematically mis-ranks opportunities.  <!-- noev: worked-example / rubric figure, not a sourced claim -->

---

## Part 3: The Prioritization Matrix — Value × Data Readiness × Complexity

Most prioritization frameworks plot value against complexity (or feasibility) on two axes. That two-axis model is where automation programs go wrong, because it hides the variable that actually kills projects: **data**. The evidence is blunt — Gartner predicts that **through 2026, organizations will abandon 60% of AI projects that are not supported by AI-ready data** ([Gartner, 2025](#ev-gartner-ai-ready-data-2025-abandonment)). Data readiness deserves its own axis precisely because it is the most common, least visible cause of failure, and because a high-value, low-complexity opportunity sitting on unusable data is a trap that two-axis scoring rates as a "quick win."

So this framework scores every opportunity on **three independent axes, each 1–5**:

**Axis A — Value** (1 = marginal, 5 = transformational). Use the net annual value from Part 2, bucketed into 1–5 bands you define for your context (e.g., 1 = <$50K, 5 = >$1M). Scoring the dollar figure into a band keeps the three axes comparable.  <!-- noev: worked-example / rubric figure, not a sourced claim -->

**Axis B — Data Readiness** (1 = data scattered/absent, 5 = real-time, governed, quality-assured). This is the workflow-scoped Dimension 3 score from Part 1, reused here. *Low data readiness is a veto, not a discount* — see sequencing below.

**Axis C — Complexity / Feasibility** (1 = simple, well-bounded, few integrations; 5 = deep cross-system integration, heavy change management, regulatory exposure). Complexity is the lever most consistently underestimated, so score it pessimistically and include *organizational* complexity (number of stakeholders, change resistance), not just technical complexity.

### How to read the three scores together

Do not collapse the three into a single weighted average — the averaging hides exactly the trade-offs you need to see. Read them as a profile:

| Value | Data readiness | Complexity | Verdict |
| --- | --- | --- | --- |
| High (4–5) | High (4–5) | Low (1–2) | **Quick win** — do first |
| High (4–5) | High (4–5) | High (4–5) | **Strategic bet** — fund deliberately, stage it |
| High (4–5) | Low (1–2) | Any | **Blocked** — fix data first (a Track 03 project), then revisit |
| Low (1–2) | Any | Low (1–2) | **Filler** — do only with spare capacity |
| Low (1–2) | Any | High (4–5) | **Defer / decline** |
| Any | Any | Any with no named owner | **Not ready** — assign ownership before scoring |

The single most important rule: **a low Data Readiness score overrides a high Value score.** A high-value opportunity on unready data is not a quick win you can muscle through — it is a data project wearing an automation costume. Routing it back to [Track 03](/enterprise-ai-transformation/tracks/03-data-readiness/index.md) as a prerequisite is the correct, money-saving move, and it is exactly the discipline the 60% abandonment figure above demands.  <!-- noev: worked-example / rubric figure, not a sourced claim -->

---

## Part 4: Sequencing Recommendations

The matrix produces four buckets. Sequence them in this order:

1. **Quick wins first (high value, ready data, low complexity).** These build credibility, free capacity, and fund the harder work. Ship two or three before touching anything ambitious. They also validate your sizing method against reality, so you trust the bigger numbers later.

2. **One strategic bet in parallel (high value, ready data, high complexity).** Pick a single end-to-end workflow worth genuinely redesigning, not just automating. This is where the McKinsey finding lives: the outsized EBIT impact comes from fundamental workflow redesign, not surface-level tool deployment. Resource it properly and stage it into milestones; do not start three at once.

3. **Data-blocked opportunities become Track 03 prerequisites, not automation projects.** For every high-value/low-data candidate, open a scoped data-readiness workstream and re-score the opportunity once the data axis reaches 3+. Track these explicitly so the value is not forgotten — it is deferred, not declined.

4. **Defer or decline the rest.** Low value with high complexity should be killed clearly so the backlog stays honest. The fastest way to lose a program's credibility is to keep a graveyard of "someday" items that quietly consume attention.

Sequencing is also a hedge against the dominant failure mode. The IBM Institute for Business Value found executives expected AI-enabled workflows to jump from **3% to 25% of operations** in a single year — an eight-fold surge in ambition ([IBM, 2025](#ev-ibm-ibv-ai-projects-profits-2025-workflow-surge)) — while Deloitte found only **25% of organizations had moved 40% or more of their AI pilots into production**, and only **30% were redesigning key processes around AI** ([Deloitte, 2026](#ev-deloitte-state-ai-enterprise-2026-production-redesign)). The gap between that ambition and that production rate is filled with poorly sequenced programs that started the hard, data-blocked, low-readiness work first. Sequencing on the three-axis profile is how you stay on the right side of that gap.

---

## How to Run the Assessment

**Assemble the right group.** No single person can score this honestly. You need: the process owner for each workflow under review; one or two people who actually *do* the work daily (they know the real volumes, variants, and rework); someone with data/system knowledge to score the data-readiness axis credibly; and a finance or analytics partner to sanity-check the sizing. Without the frontline doers in the room, maturity Dimensions 1, 2, and 5 will be systematically over-scored. Budget 90 minutes for maturity scoring and a separate working session per cluster of opportunities for sizing.

**Score maturity first, opportunities second.** The maturity result determines whether you are even ready to pursue opportunities (Level 3+) or whether the honest answer is "fix the foundations first." Do not skip to the exciting opportunity list — a Level 1–2 function should be building visibility, standardization, and measurement before automating anything.

**Size on evidence, not optimism.** Every value estimate needs a named source for its volume, time, and error figures — a system report, a sampled time study, an error log. "We think it's about an hour" is not a baseline. The sizing is only as credible as the worst-supported number in it.

**Score complexity pessimistically.** Underestimated complexity is one of the three classic prioritization failures. When the room is split between a 3 and a 4 on complexity, choose 4. Include integration count, regulatory exposure, and change resistance.

**Re-score on a cadence.** Maturity and data readiness move. Put a re-score date — typically 90 days out, or when a blocked data project completes — on the calendar before the session ends.

---

## Scoring Templates

**Maturity scoring (per function):**

| Dimension | Score (1–5) | Supporting evidence | Key gap | Action to raise |
| --- | --- | --- | --- | --- |
| Process Visibility | | | | |
| Workflow Standardization | | | | |
| Data Readiness for the Workflow | | | | |
| Automation and AI Capability | | | | |
| Change and Adoption Readiness | | | | |
| Measurement Discipline | | | | |
| **Average** | | | | |

**Opportunity scoring (per candidate workflow):**

| Workflow | Net annual value ($) | Value (1–5) | Data readiness (1–5) | Complexity (1–5) | Verdict | Owner | Next step |
| --- | --- | --- | --- | --- | --- | --- | --- |
| | | | | | | | |

Interpreting the maturity average:

- **1.0–2.0 (Opaque/Aware):** Do not pursue an opportunity backlog yet. Invest in visibility, standardization, and measurement — the foundations that make sizing and redesign possible.
- **2.0–3.0 (Aware/Capable):** Pursue a small number of quick wins to build capability while raising the lowest dimension; do not attempt a strategic bet yet.
- **3.0–4.0 (Capable/Optimizing):** Run the full prioritization matrix; pursue quick wins plus one strategic bet; route data-blocked items to Track 03.
- **4.0–5.0 (Optimizing/Adaptive):** Scale the portfolio; the constraint is throughput and sequencing discipline, not readiness.

---

## What to Do With the Results

The most common failure mode is the same one that afflicts every assessment: a score gets produced, presented once, and filed. The score is not the output. The **ranked opportunity list with owners and sequence** is the output.

**Convert the matrix into a funded sequence within two weeks.** Quick wins get started immediately; the strategic bet gets a scoped charter; data-blocked items get Track 03 workstreams opened against them. If nothing on the list has a named owner and a start date within two weeks of the session, the assessment changed nothing.

**Use the data-readiness axis to stop bad funding decisions before they happen.** The single most valuable thing this assessment does is catch the high-value, low-data opportunity that two-axis scoring would have greenlit — and reroute it to fix the data first. That is the discipline behind the 60% abandonment figure: the projects that fail were mostly fundable-looking ideas sitting on unusable data. Every time this assessment blocks one of those, it pays for itself.  <!-- noev: worked-example / rubric figure, not a sourced claim -->

**Feed the strategic bet into a genuine redesign, not a veneer.** The maturity rubric and the sizing both exist to support the one move that the evidence says actually moves EBIT: fundamentally redesigning a workflow rather than bolting AI onto the existing one. Hand the strategic bet to the [practitioner guide for running a workflow optimization program](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/05-practitioner-guide-running-a-workflow-optimization-program.md) and instrument it with [Track 08](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md) baselines from day one.

**Put the re-score on the calendar.** Maturity and data readiness change as foundational work completes; a blocked opportunity today may be a quick win next quarter. A program that does not re-score has no mechanism to promote its own backlog.

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **MIT Project NANDA — *The GenAI Divide: State of AI in Business 2025*, 2025.** Just 5% of integrated AI pilots are extracting millions in value, while the vast majority remain stuck with no measurable P&L impact. [View source](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf){#ev-mit-nanda-genai-divide-2025-no-pl-impact} · verified 2026-06-20 · ⚠ secondary mirror
- **McKinsey — *The State of AI in 2025*, 2025.** AI high performers are 2.8 times more likely to report fundamental workflow redesign than other organizations (55% versus 20%). [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-workflow-redesign-highperf} · verified 2026-06-20 · primary
- **Deloitte — *Global Process Mining Survey*, 2025.** 59 percent expect cost savings, up from 46 percent; process transparency (51 percent) and process monitoring (41 percent) are next, followed by automation identification (38 percent). [View source](https://www.deloitte.com/de/de/services/consulting-financial/research/global-process-mining-survey.html){#ev-deloitte-process-mining-survey-2025-objectives} · verified 2026-06-20 · ⚠ secondary mirror
- **ServiceNow — *How to use Process Mining to identify automation opportunities*, 2024.** look for tasks that take anywhere between 2 and 30 minutes to complete. [View source](https://www.servicenow.com/community/process-mining-blog/how-to-use-process-mining-to-identify-automation-opportunities/ba-p/3061642){#ev-servicenow-process-mining-2024-task-profile} · verified 2026-06-20 · primary
- **Gartner — *Lack of AI-Ready Data Puts AI Projects at Risk*, 2025.** Through 2026, organizations will abandon 60% of AI projects unsupported by AI-ready data. [View source](https://www.gartner.com/en/newsroom/press-releases/2025-02-26-lack-of-ai-ready-data-puts-ai-projects-at-risk){#ev-gartner-ai-ready-data-2025-abandonment} · verified 2026-06-20 · primary
- **IBM Institute for Business Value — *From AI Projects to Profits*, 2025.** respondents expect AI-enabled workflows to grow from 3% today to 25% by the end of 2025. [View source](https://www.ibm.com/thought-leadership/institute-business-value/en-us/report/agentic-ai-profits){#ev-ibm-ibv-ai-projects-profits-2025-workflow-surge} · verified 2026-06-20 · primary
- **Deloitte — *State of AI in the Enterprise 2026*, 2026.** only 25% of respondents have moved 40% or more of their AI pilots into production; only 30% of organizations are redesigning key processes around AI. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-ai-report-2026.html){#ev-deloitte-state-ai-enterprise-2026-production-redesign} · verified 2026-06-20 · primary
