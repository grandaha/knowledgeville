---
type: Concept
title: Workflow Optimization Framework
description: "How to identify and prioritize AI-enabled workflows across the four levels of integration, with process discovery methodology, ROI framing, and cross-track connections."
tags: [workflow-optimization, automation, prioritization, process-discovery, roi]
timestamp: "2026-06-17"
---

## Why This Matters Now

Enterprises have crossed the adoption threshold for AI but not the value threshold. By 2025, **78% of organizations reported using AI in at least one business function**, up from 55% in 2023 *(McKinsey, State of AI, 2025)*. Yet adoption has badly outrun realized return. In the same survey, **only 39% of organizations could attribute any enterprise-level EBIT impact to AI** — and most of those put the contribution at less than 5% of EBIT *(McKinsey, State of AI, 2025)*. The work has been deployed almost everywhere and is paying off almost nowhere at scale.

The gap is not a technology gap. It is a workflow gap. AI tools get bolted onto tasks while the surrounding process — the sequence of steps, handoffs, decisions, exceptions, and systems that actually constitutes the work — is left untouched. A faster draft of an email inside a process that still routes through four manual approvals does not move the P&L. The organizations that capture value are the ones that treat the *workflow*, not the tool, as the unit of optimization: they find the workflows worth changing, decide how far to push automation on each, and instrument the result so the value is visible.

This page is the organizing framework for that work. It covers how to identify and prioritize AI-enabled workflows, introduces the four levels of workflow AI integration (Assist → Automate → Augment → Agent), lays out a process discovery methodology, frames how to size and defend the investment, and shows how workflow optimization depends on the data and platform tracks. It is the *what to optimize and in what order* layer; the sibling pages tell you how far to push each workflow, what tools to use, and how to run the program.

---

## The Value Gap: Why Most Automation Never Pays Off

Before prioritizing workflows, it helps to understand precisely how value leaks out, because the failure modes are remarkably consistent across two decades of automation waves — and they shape the framework that follows.

The headline number for the current wave is stark. MIT's Project NANDA reviewed more than 300 AI initiatives and concluded that **roughly 95% of enterprise generative-AI pilots were delivering no measurable impact on the P&L**, with only about 5% achieving rapid value *(MIT Project NANDA, The GenAI Divide: State of AI in Business, 2025)*. This is not an isolated finding. Gartner predicted that **at least 30% of generative-AI projects would be abandoned after proof of concept by the end of 2025**, citing poor data quality, inadequate risk controls, escalating costs, and unclear business value *(Gartner, 2024)*. BCG found that **74% of companies struggle to achieve and scale value from AI**, with only about 4% generating substantial value across functions *(BCG, AI Adoption in 2024, 2024)*.

> **~95% of enterprise generative-AI pilots** were delivering no measurable impact on the P&L *(MIT Project NANDA, The GenAI Divide: State of AI in Business, 2025)*.

None of this is new. The previous automation wave — robotic process automation (RPA) — failed in the same shape. EY estimated that **30% to 50% of initial RPA projects failed** *(EY, Get Ready for Robots, 2016/2017)*. A survey of 400 senior executives found that **38% said RPA projects failed because they were too complex** and **30% said they failed because the process or the tools were not understood** *(ABBYY, 2020)*. And scaling was vanishingly rare: Deloitte's global RPA survey found that **only 3–4% of organizations had scaled their digital workforce beyond 50 bots** *(Deloitte, Global RPA Survey, 2018)*. The pattern repeats because the root cause is the same: organizations automate a process they have not actually understood, standardized, or instrumented. The technology changes; the discipline that is missing does not.

The practical lesson for prioritization is that **the binding constraint is rarely model capability — it is process readiness and the path to scale.** A workflow that is poorly understood, full of undocumented exceptions, dependent on dirty data, or lacking an owner will not produce value no matter how capable the AI. The framework below is built to surface those conditions *before* the investment, not after.

---

## How to Identify and Prioritize AI-Enabled Workflows

### Start by separating tasks, processes, and workflows

The first discipline is to be precise about the unit you are optimizing, because conflating these three is a primary source of disappointment. APQC's Process Classification Framework offers a clean taxonomy: a five-level hierarchy running **Category → Process Group → Process → Activity → Task**, where a task is the atomic "element of work that goes into executing an activity" *(APQC, Understanding the PCF, 2018)*. The PCF is deliberately a *classification* taxonomy, not a sequence model.

For our purposes:

- A **task** is the atomic unit — drafting a paragraph, extracting a field from an invoice, classifying a ticket. AI tools are very good at tasks.
- A **process** is the named, repeatable end-to-end objective — "procure-to-pay," "claims adjudication," "employee onboarding."
- A **workflow** is the *orchestration* layer the PCF omits: the actual sequence of tasks, handoffs between people and systems, decision branches, and exception paths through which a process runs.

The reason this matters: most AI value claims are measured at the task level (a 25% faster draft), but P&L value is realized at the workflow level (a cycle that completes faster, with fewer errors, at lower cost). McKinsey's work reinforces the point — its analysis scores work *activities*, not occupations, finding that current technologies "have the potential to automate work activities that absorb **60 to 70 percent** of employees' time today" *(McKinsey/MGI, The Economic Potential of Generative AI, 2023)*. A 60–70% activity-automation ceiling does not translate into 60–70% of jobs or even of any single workflow; it accumulates only when the surrounding workflow is redesigned to capture the freed-up time.

### Prioritize on two axes: value and feasibility

With the right unit in view, prioritize candidate workflows on two independent axes.

**Value** — how much is this workflow worth changing? Size it on:

- **Volume and frequency** — how many times the workflow runs per period. High-volume, high-frequency workflows compound small per-run gains into material totals.
- **Time and cost per run** — labor hours, cycle time, and cost-per-transaction consumed.
- **Error and rework rate** — the cost of mistakes, exceptions, and downstream correction.
- **Strategic weight** — customer-facing impact, risk exposure, or bottleneck status (a workflow that gates others is worth more than its own cost suggests).

**Feasibility** — how ready is this workflow to be changed? Drawing on the canonical automation-screening criteria from the research literature — **standardization, rule-based logic versus judgment, availability of digital input, process stability, and exception rate** *(arXiv, A framework to evaluate the viability of RPA, 2020)* — assess:

- **Standardization and stability** — is the workflow consistent, or does every run differ?
- **Rule-based vs. judgment** — deterministic, rule-bound steps are far easier than open-ended judgment (though generative AI extends the frontier into language-based judgment, covering activities at roughly 25% of work time per *(McKinsey/MGI, 2023)*).
- **Digital, accessible input** — is the data the workflow consumes already digital, structured, and reachable? This is where the data-readiness track becomes a hard dependency.
- **Exception density** — workflows that are 80% standard and 20% chaotic exceptions are deceptively hard; the exceptions, not the happy path, determine effort.

Plot candidates on a value-versus-feasibility grid. The sequencing rule is unglamorous but reliable: **high-value, high-feasibility workflows first** — these fund the program and build credibility — followed by high-value, lower-feasibility workflows that justify the harder data and process work. Low-value workflows are deprioritized regardless of how easy they are to automate, which is the single most common prioritization error: automating what is easy rather than what matters.

| Prioritization quadrant | Value | Feasibility | Action |
|---|---|---|---|
| **Quick wins** | High | High | Do first — fund the program, prove the model |
| **Strategic bets** | High | Low | Sequence next — invest in data/process readiness to unlock |
| **Fill-ins** | Low | High | Only if near-zero marginal effort; beware the "easy but pointless" trap |
| **Avoid** | Low | Low | Do not pursue |

---

## The Four Levels of Workflow AI Integration

For each prioritized workflow, the next decision is *how far to push the integration*. A single binary "automate or not" obscures a spectrum. This framework uses four levels — **Assist → Automate → Augment → Agent** — each representing a greater degree of AI autonomy and a different risk, governance, and value profile.

| Level | What it means | AI's role | Human's role |
|---|---|---|---|
| **Assist** | AI helps a human do a step faster or better | Suggests, drafts, summarizes | Performs and decides; does every step |
| **Automate** | AI executes a defined, bounded step end-to-end | Executes deterministic, rule-bound steps | Designs, supervises, handles exceptions |
| **Augment** | AI and human jointly own the workflow, each on their strengths | Handles routine volume and analysis | Owns judgment, escalations, edge cases |
| **Agent** | AI plans and executes a multi-step workflow toward a goal | Plans, acts across systems, self-corrects | Sets goals, sets guardrails, audits outcomes |

The evidence base spans the spectrum. At the **Assist** level, controlled studies are strong: consultants using GPT-4 completed **12.2% more tasks, 25.1% faster, with results rated over 40% higher in quality** *(Harvard Business School / BCG, Navigating the Jagged Technological Frontier, 2023)*, and developers using GitHub Copilot completed a coding task **55.8% faster** than a control group *(Peng et al., arXiv, 2023)*. At the **Augment** level, a field study of customer-support agents found a **14% average increase in issues resolved per hour, rising to 34% for novice agents** *(Brynjolfsson, Li & Raymond, NBER, 2023)*. The **Agent** level is where the market is now racing — Gartner predicts that **40% of enterprise applications will feature task-specific AI agents by 2026, up from less than 5% in 2025** *(Gartner, 2025)* — and also where governance risk concentrates, because the AI is acting across systems rather than suggesting to a human.

Choosing the right level is itself a value-and-risk judgment: pushing a high-judgment, high-stakes workflow straight to Agent is how pilots become incidents, while leaving a high-volume deterministic workflow at Assist leaves most of the value on the table. The full decision model — how to choose a level per workflow, the governance implications of each, and how to progress a workflow up the levels over time — is detailed in [the four levels of workflow AI integration](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md).

---

## Process Discovery Methodology

Prioritization is only as good as the picture of how work actually flows — and that picture is almost never the one in the process documentation. Process discovery is the discipline of reconstructing the real workflow before you change it. There are three complementary methods, best used together.

**1. Process mapping (the intended process).** Workshops, interviews, and BPMN diagramming capture how people *believe* the workflow runs. This is fast and essential for shared understanding, but it is subjective, a snapshot in time, and systematically blind to the variants and rework that nobody admits to.

**2. Process mining (the real end-to-end process).** Process mining reconstructs the actual execution from event-log data — the timestamps and activity records left in ERP, CRM, ticketing, and other transactional systems. Academically, it "aims to discover, monitor and improve real processes by extracting knowledge from event logs," via three operations: **discovery, conformance checking, and enhancement** *(IEEE Task Force on Process Mining, Process Mining Manifesto, 2012)*. It exposes the variants, bottlenecks, and rework loops that mapping misses. Its value is well evidenced: a Forrester study of a composite Celonis customer found **383% three-year ROI with payback in under six months**, including one workflow where no-touch processing rose **53 percentage points (from 33% to 86%)** *(Forrester Consulting, commissioned by Celonis, 2025)*. Named results are larger still — Deutsche Telekom reported **over €66M saved** in procure-to-pay and GE Healthcare a **$1.3B free-cash-flow increase in a single year** *(Celonis customer stories)* — though as single-vendor figures these are illustrative rather than benchmarks. The catch is universal: mining is only as good as the event log, and extracting, cleaning, and mapping that log (case ID, activity, timestamp) is the bulk of the work — another reason data readiness gates the whole effort.

**3. Task mining (the desktop reality).** Where process mining draws on transactional system logs, task mining captures user-interaction data — clicks, keystrokes, copy-paste, application time — to reconstruct how work is performed at the desktop, below the level any system log records *(Celonis, What is Task Mining)*. It is how you find the invisible swivel-chair work between systems that is often the richest automation candidate.

The methodology in practice: **map to align, mine to verify, task-mine to find the hidden work — then prioritize against the value/feasibility grid above using evidence, not anecdote.** Discovery is where the "process not understood" failure mode (the 30% of RPA failures cited earlier) is defeated.

---

## ROI Framing for Workflow Investment

A workflow investment has to be sized and defended in financial terms, both to win funding and to make value realization measurable rather than aspirational.

### Sizing the value

Build the value case from the workflow's own measurable mechanics, not from headline industry figures:

- **Labor/capacity freed** — FTE-hours saved per run × runs per period, valued at loaded cost. McKinsey's value-by-function work is a useful sanity check on magnitude: it estimates generative AI could add **$2.6–4.4 trillion annually** across use cases, with productivity gains of **30–45% of function cost in customer operations** and **20–45% in software engineering** *(McKinsey/MGI, The Economic Potential of Generative AI, 2023)*. Treat these as ceilings for whole functions, not promises for one workflow.
- **Cycle-time reduction** — faster completion converts to revenue (faster cash, better experience) or cost (less work-in-progress). Klarna reported its AI assistant cut customer-service resolution time from **11 minutes to under 2 minutes** while handling the equivalent of **700 FTEs** of work *(Klarna, 2024)* — a self-reported example, but a clear illustration of cycle-time value.
- **Error and rework reduction** — fewer exceptions and corrections. Quantify this from your own discovery data; credible cross-industry percentages for error reduction are genuinely scarce in primary research, so size it from your measured baseline rather than an imported figure.

### Framing the return — and the payback reality

On the optimistic side, IDC's analysis found organizations realizing **an average of $3.70 in return per $1 invested in generative AI, rising to $10.30 for the top adopters** *(IDC, commissioned by Microsoft, 2024)*, and a Google Cloud study reported **74% of executives achieving ROI within the first year** *(Google Cloud, ROI of AI Study, 2025)*. Both are sponsored studies and skew toward leaders — useful as directional ceilings, not base cases.

The sober counterweight matters more for credible planning. Deloitte found that organizations scaling automation beyond piloting achieved an average **32% cost reduction** in the areas targeted (up from 24% in 2020) — but also that **36% had not calculated their payback at all**, and that average payback for pilot-stage intelligent automation had *lengthened* to about **22 months, up from 16 months in 2020**, as the easy wins were exhausted *(Deloitte, Automation with Intelligence, 2022/2024)*. The honest ROI framing, therefore, is a barbell: quick wins can pay back in well under a year, but the strategic, harder workflows carry multi-year paybacks and demand the data and platform investment to be counted in the case.

The discipline that separates the 39% who see EBIT impact from the rest is **instrumenting the baseline before you start** — current cycle time, cost-per-transaction, error rate, and volume — so the delta is measurable. Value that is not measured against a baseline is value that, by Deloitte's evidence, a third of organizations never actually calculate. The measurement methodology itself is the subject of [Track 08, measurement and value realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md).

---

## How Workflow Optimization Connects to the Other Tracks

Workflow optimization is not a standalone effort; it sits on top of two enabling tracks and feeds two governing ones. Treating it as independent is itself a failure mode.

- **Data readiness (Track 03) is a hard dependency.** Every method above — process mining's event logs, an AI step's input data, an agent's context — depends on data that is accessible, structured, and trustworthy. Gartner named poor data quality among the top reasons projects are abandoned after POC *(Gartner, 2024)*. A workflow's *feasibility* score is, in large part, a data-readiness score. See [Track 03, data readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md).
- **Platform (Track 04) is how it runs at scale.** Moving a workflow from a clever pilot to reliable production — orchestration, integration across systems, monitoring, evaluation — is platform work. The 3–4% RPA scaling rate and the pilot-to-production gap are platform failures as much as anything. See [Track 04, technology architecture and platform](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/index.md).
- **Governance (Track 02) gates the higher levels.** As workflows move up the Assist → Agent spectrum, the AI takes more autonomous action and governance risk rises sharply. Any workflow that automates a decision-bearing or customer-facing step falls under [Track 02, AI governance and risk](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/index.md).
- **Measurement (Track 08) closes the loop.** Sizing value up front and proving it after deployment is measurement-track work; without it, ROI claims stay aspirational. See [Track 08, measurement and value realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md).

For the tools that support each method here — mapping, mining, automation platforms, and agent frameworks — see the [tooling landscape](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/04-tooling-landscape.md). To run an actual program end to end, see the [practitioner guide](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/05-practitioner-guide-running-a-workflow-optimization-program.md), and to score your own portfolio, use the [workflow maturity and opportunity assessment](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/06-assessment-workflow-maturity-and-opportunity-scoring.md).

---

## Common Failure Modes

The research above points to a recurring set of traps. Each maps to a discipline in this framework.

- **Automating the easy, not the valuable.** Chasing high-feasibility, low-value workflows because they are simple. This is why prioritization runs on two axes, not one — feasibility alone is a trap.
- **Optimizing the task, ignoring the workflow.** Deploying a faster tool inside an unchanged process. Task-level gains do not reach the P&L until the surrounding workflow is redesigned; this is the core of the 39%-EBIT-impact gap.
- **Automating a process you never understood.** Skipping discovery and automating the documented (and fictional) happy path while exceptions break in production — the 30% of RPA failures attributed to the process not being understood *(ABBYY, 2020)*.
- **Pilot purgatory.** Running endless POCs with no path to production. Roughly 95% of generative-AI pilots showed no P&L impact *(MIT Project NANDA, 2025)* largely because scaling was never designed in — a platform and ownership failure, not a model one.
- **Pushing the autonomy level too far, too fast.** Sending a high-judgment workflow straight to Agent without the governance to contain it — turning pilots into incidents.
- **No instrumented baseline.** Launching without measuring current cycle time, cost, error rate, and volume — leaving value uncalculated, as 36% of organizations do *(Deloitte, 2022)*.
- **Treating the program as standalone.** Ignoring the data, platform, and governance dependencies that determine whether anything scales.

---

## Closing Checklist

Before committing to a workflow optimization investment, confirm:

- [ ] **Unit is clear** — you are optimizing a *workflow* (orchestration), not just a task, and you know which process it belongs to.
- [ ] **Discovery is evidence-based** — the real workflow has been mapped, mined, and task-mined; you are not working from the documented fiction.
- [ ] **Prioritized on two axes** — the workflow ranks high on *both* value and feasibility, or is a deliberate strategic bet with a readiness plan.
- [ ] **Integration level chosen deliberately** — the Assist → Automate → Augment → Agent level matches the workflow's judgment and risk profile.
- [ ] **Baseline instrumented** — current cycle time, cost-per-transaction, error rate, and volume are measured, so the delta will be provable.
- [ ] **ROI case is honest** — value sized from the workflow's own mechanics, with realistic (often multi-year) payback for the harder bets, not headline ceilings.
- [ ] **Dependencies confirmed** — data is accessible and trustworthy (Track 03), there is a path to production at scale (Track 04), governance covers the autonomy level (Track 02), and measurement is wired in (Track 08).
- [ ] **Ownership assigned** — a named owner accountable for the workflow's outcome, not just its launch.

---

## Sources

- McKinsey & Company (QuantumBlack) — *The State of AI in 2025: Agents, Innovation, and Transformation* — 2025 (https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)
- McKinsey Global Institute — *The Economic Potential of Generative AI: The Next Productivity Frontier* — 2023 (https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/the-economic-potential-of-generative-ai-the-next-productivity-frontier)
- MIT Project NANDA (MIT Media Lab) — *The GenAI Divide: State of AI in Business 2025* — 2025 (https://fortune.com/2025/08/18/mit-report-95-percent-generative-ai-pilots-at-companies-failing-cfo/)
- Gartner — *Gartner Predicts 30% of Generative AI Projects Will Be Abandoned After Proof of Concept by End of 2025* — 2024 (https://thejournal.com/articles/2024/08/06/gartner-30-of-gen-ai-projects-will-be-abandoned.aspx)
- Gartner — *Gartner Predicts 40% of Enterprise Apps Will Feature Task-Specific AI Agents by 2026, Up From Less Than 5% in 2025* — 2025 (https://www.gartner.com/en/newsroom/press-releases/2025-08-26-gartner-predicts-40-percent-of-enterprise-apps-will-feature-task-specific-ai-agents-by-2026-up-from-less-than-5-percent-in-2025)
- BCG — *AI Adoption in 2024: 74% of Companies Struggle to Achieve and Scale Value* — 2024 (https://www.cfodive.com/news/only-4-companies-reap-full-value-ai-bcg-artificial-intelligence/730982/)
- EY — *Get Ready for Robots: Why Planning Makes the Difference Between Success and Disappointment* — 2016/2017 (https://www.advsyscon.com/blog/why-rpa-fails-robotic-process-automation/)
- ABBYY — *Survey of 400 senior executives on RPA project failure* — 2020 (https://www.ciodive.com/news/rpa-robotic-process-automation-failures/577917/)
- Deloitte — *Global RPA Survey 2018* — 2018 (https://legaltechnology.com/2018/10/11/deloitte-rpa-report-admits-surprise-at-lack-of-vision-and-it-readiness/)
- Deloitte — *Automation with Intelligence (Global Intelligent Automation Survey)* — 2022/2024 (https://www.deloitte.com/us/en/insights/topics/talent/intelligent-automation-2022-survey-results.html)
- APQC — *Understanding the Elements of APQC's Process Classification Framework* — 2018 (https://www.apqc.org/sites/default/files/files/PCF%20Collateral/Understanding%20the%20PCF%20Elements%20-%20FINAL.pdf)
- IEEE Task Force on Process Mining (W. van der Aalst et al.) — *Process Mining Manifesto* — 2012 (https://pure.tue.nl/ws/files/3707913/671825010972295.pdf)
- arXiv — *A Framework to Evaluate the Viability of Robotic Process Automation for Business Process Activities* — 2020 (https://arxiv.org/pdf/2007.10900)
- Forrester Consulting (commissioned by Celonis) — *The Total Economic Impact of Celonis Process Intelligence* — 2025 (https://www.celonis.com/news/press/celonis-customers-saw-payback-in-6-months-and-383-roi)
- Celonis — *Deutsche Telekom Procure-to-Pay Process Mining (customer story)* — 2024 (https://www.celonis.com/solutions/stories/deutsche-telekom-procure-to-pay-process-mining)
- Celonis — *How GE Healthcare Boosted Free Cash Flow by $1.3B (case study)* — 2024 (https://www.celonis.com/blog/how-ge-healthcare-boosted-free-cash-flow)
- Celonis — *What Is Task Mining* — 2024 (https://www.celonis.com/insights/topics/what-is-task-mining)
- IDC (commissioned by Microsoft) — *The Business Opportunity of AI: Generative AI Delivering New Business Value and Increasing ROI* — 2024 (https://news.microsoft.com/en-xm/2025/01/14/generative-ai-delivering-substantial-roi-to-businesses-integrating-the-technology-across-operations-microsoft-sponsored-idc-report/)
- Google Cloud — *ROI of AI Study (2nd annual)* — 2025 (https://www.prnewswire.com/news-releases/google-cloud-study-reveals-52-of-executives-say-their-organizations-have-deployed-ai-agents-unlocking-a-new-wave-of-business-value-302546045.html)
- Harvard Business School / BCG (Dell'Acqua, McFowland, Mollick et al.) — *Navigating the Jagged Technological Frontier* — 2023 (https://mitsloan.mit.edu/sites/default/files/2023-10/SSRN-id4573321.pdf)
- Brynjolfsson, Li & Raymond — *Generative AI at Work* (NBER Working Paper 31161) — 2023 (https://www.nber.org/papers/w31161)
- Peng, Kalliamvakou, Cihon & Demirer — *The Impact of AI on Developer Productivity: Evidence from GitHub Copilot* (arXiv:2302.06590) — 2023 (https://arxiv.org/abs/2302.06590)
- Klarna — *Klarna AI Assistant Handles Two-Thirds of Customer Service Chats in Its First Month* — 2024 (https://www.klarna.com/international/press/klarna-ai-assistant-handles-two-thirds-of-customer-service-chats-in-its-first-month/)
