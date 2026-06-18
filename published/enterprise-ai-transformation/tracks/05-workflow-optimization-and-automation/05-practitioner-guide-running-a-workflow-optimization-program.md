---
type: Playbook
title: "Practitioner Guide: Running a Workflow Optimization Program"
description: "How to run a workflow optimization program end to end: discovery and prioritization, redesigning workflows with AI in the loop, change management, and post-deployment measurement."
tags: [workflow-optimization, change-management, automation, practitioner-guide, process-mining]
timestamp: "2026-06-17"
---

## What this guide is for

This guide is written for the operations leader, transformation lead, or workflow program owner who has been handed a mandate that sounds like "use AI to make our processes faster." That mandate arrives in many forms — a board directive to "do something with AI," a cost-reduction target, a backlog of teams asking for automation, or the uncomfortable realization that competitors are moving faster. All of those converge on the same underlying work: deciding which workflows to change, redesigning them so AI actually helps rather than merely sits on top, moving the people who run those workflows through the transition, and proving the change paid off.

This guide assumes you are not starting from zero on AI capability. The strategy, governance, platform, and data foundations are covered in other tracks; this guide is about the operational discipline of running an optimization program against real workflows. It is deliberately opinionated, because the failure modes here are well documented and expensive. The dominant lesson from a decade of automation programs is not that the technology fails — it is that organizations automate the wrong things, automate them badly, fail to bring people along, and never measure whether anything improved.

What this guide produces is a runnable program in four phases: a prioritized portfolio of workflow opportunities backed by evidence rather than opinion (Phase 1), redesigned workflows with humans deliberately kept in the loop (Phase 2), a change effort that gets the people doing the work to actually adopt the new way (Phase 3), and an instrumented measurement loop that tells you whether to scale, fix, or kill each initiative (Phase 4). The phases are sequential per workflow but run as a rolling pipeline across a portfolio — you are always discovering the next batch while building and measuring the current one.

The stakes are high enough to state plainly up front. A 2025 MIT study of enterprise generative-AI deployments found that roughly 95% of pilots delivered little to no measurable impact on profit and loss, with only about 5% capturing substantial value (MIT NANDA, 2025). The gap between those two groups is almost never the model. It is the program discipline this guide is about.

---

## Phase 1: Discovery and prioritization (weeks 1–4)

The goal of Phase 1 is a prioritized portfolio of workflow opportunities, each with a documented baseline and a clear hypothesis about what AI changes and why. The single most common reason optimization programs fail is that they skip this phase — they start with a tool or a flashy use case and reverse-engineer a justification. You want the opposite: evidence first, solution second.

### Why discovery is worth four weeks

Most organizations badly underestimate how much of their actual work is invisible. Processes drift from their documented versions, exception paths multiply, and a surprising share of effort goes to work nobody designed. McKinsey's foundational automation research found that about half of all work activities are technically automatable with demonstrated technology, and that roughly 60% of occupations have at least 30% of their constituent activities automatable — meaning the opportunity is distributed across tasks within roles, not concentrated in whole jobs you can simply eliminate (McKinsey Global Institute, *A Future That Works*, 2017). Generative AI raised that ceiling considerably: McKinsey later estimated that current technologies including gen AI could automate activities absorbing 60–70% of employees' time today (McKinsey Global Institute, *The economic potential of generative AI*, 2023). The point of discovery is to find where, in your specific organization, that potential actually lives.

There is real waste to recover. Knowledge workers spend roughly a fifth of the workweek — about 19% — just searching for internal information (McKinsey Global Institute, *The Social Economy*, 2012). That is the kind of diffuse, hard-to-see drain that disciplined discovery surfaces and a redesigned workflow can attack.

### Run a discovery sprint

Structure discovery as a focused sprint, not an open-ended assessment that drags for a quarter. The deliverable is a ranked opportunity list, and the sprint should produce it in three to four weeks.

- **Frame the scope.** Pick one or two business areas (a department, a function, an end-to-end process such as order-to-cash). A program that tries to discover everything at once discovers nothing usefully.
- **Go to the work.** Interview five to ten people who actually run the workflows, and watch them work. Ask what slows them down, where they wait, what they redo, and which tasks they would happily never do again. The friction people complain about is your richest signal.
- **Map the current state.** For each candidate workflow, document the steps, the handoffs, the systems touched, the volume (how many times per day/week), the cycle time, the error/rework rate, and the people involved. This map is also your baseline — capture the numbers now, because once you change the workflow you will never recover a clean "before."

### Use process and task mining where the volume justifies it

For high-volume, system-mediated workflows, do not rely on interviews alone — interviews capture what people think they do, not what the event logs show actually happens. Process mining (reconstructing the real process from system event logs) and task mining (capturing desktop-level actions) reveal the hidden variants, rework loops, and bottlenecks that nobody describes in an interview. The discipline has gone mainstream: the worldwide process-mining software market reached roughly $872 million in 2023 and is forecast to grow past $2 billion by 2028 (Gartner, cited in Process Excellence Network, 2025). And it measurably accelerates discovery — in Deloitte's intelligent-automation research, 63% of respondents said process intelligence sped up the discovery of automation use cases, versus 7% who said it slowed them down (Deloitte, *Global Intelligent Automation Survey*, 2020).

> Discovery is not optional overhead. In Deloitte's research, 63% of organizations reported that process intelligence accelerated the discovery of automation opportunities — and the firms that skip discovery are precisely the ones that end up automating processes they never understood (Deloitte, *Global Intelligent Automation Survey*, 2020).

### Prioritize with a value/feasibility lens

Once you have candidates with baselines, score them. A simple two-axis model is enough to start: **value** (volume × time saved per instance × cost per hour, plus quality and risk-reduction benefits) against **feasibility** (data availability, process standardization, technical complexity, and change difficulty). Plot the candidates, and pursue the high-value/high-feasibility quadrant first.

Two prioritization rules earn their place from hard experience. First, **deprioritize any workflow that is not yet standardized.** Automating a chaotic process locks in the chaos — more on this in the failure-patterns section. Second, **weight change difficulty explicitly.** A technically easy automation in a politically resistant team will fail; a moderately hard one in a willing team will succeed. Feasibility is as much organizational as technical.

**Phase 1 deliverable:** a prioritized opportunity portfolio. For each selected workflow: a current-state map, a documented quantitative baseline (volume, cycle time, error/rework rate, cost), a value/feasibility score, and a one-paragraph hypothesis stating what AI will change and the expected outcome. Pair this with the [Workflow Maturity & Opportunity Scoring assessment](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/06-assessment-workflow-maturity-and-opportunity-scoring.md) to pressure-test your ranking.

---

## Phase 2: Redesign and build with AI in the loop (weeks 5–10+)

The goal of Phase 2 is a redesigned workflow — not the old workflow with an AI step bolted on. This distinction is the single biggest determinant of whether the program delivers value, and the data on it is unusually clear.

### Don't pave the cow path

The instinct under deadline pressure is to take the existing process and insert AI wherever a step looks automatable. This is "paving the cow path" — formalizing an inefficient route instead of asking whether the route should exist at all. The warning is as old as business computing: as Bill Gates put it, "automation applied to an efficient operation will magnify the efficiency [and] automation applied to an inefficient operation will magnify the inefficiency" (Gates, *The Road Ahead*, 1996).

The modern evidence is striking. In McKinsey's 2025 State of AI survey, among 25 organizational attributes tested, **fundamentally redesigning workflows had the single biggest effect on whether an organization saw EBIT impact from generative AI**, and AI high performers were far more likely to have redesigned workflows rather than layered AI onto existing ones (McKinsey, *The state of AI: How organizations are rewiring to capture value*, 2025). Yet the previous year, only 21% of organizations using gen AI said they had fundamentally redesigned even some workflows (McKinsey, *The state of AI in early 2024*, 2024) — meaning roughly four in five were bolting AI on without rethinking the work. The redesign gap is exactly where the value gap comes from.

So the first redesign question is never "where do we insert AI?" It is "if we were designing this workflow today, knowing what AI can now do, how would the work flow?" Then build toward that target state. Eliminate steps that exist only to compensate for a constraint AI removes. Collapse handoffs. Move quality checks earlier.

### Keep the human in the loop — by design, not by accident

Full autonomy is rarely the right starting point, and the research on AI augmentation explains why. Where AI augments skilled humans, the gains are large and real:

| Study | Setting | Result |
|---|---|---|
| Brynjolfsson, Li & Raymond — *Generative AI at Work* (NBER, 2023) | Customer-support agents | +14% issues resolved per hour on average; +34% for novice agents |
| Dell'Acqua et al. — *Navigating the Jagged Technological Frontier* (HBS/BCG, 2023) | Management consultants, tasks within AI's frontier | +12.2% tasks completed, 25.1% faster, >40% higher quality |
| GitHub — *Quantifying Copilot's impact* (2022) | Software developers | 55% faster on a defined coding task |

But the same consulting study contains the warning: on a task deliberately chosen to fall *outside* AI's competence, consultants using AI were **19 percentage points less likely to reach the correct answer** than those working without it (Dell'Acqua et al., HBS/BCG, 2023). AI applied confidently to the wrong task degrades performance. That is the entire case for designing the human checkpoint deliberately rather than hoping people will catch errors.

Practical human-in-the-loop design:

- **Match the integration level to the stakes.** Low-risk, reversible tasks can run with light review; high-stakes or irreversible decisions need an explicit human approval gate. The [Four Levels of Workflow AI Integration](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md) gives you a vocabulary for choosing the right level per step.
- **Make review meaningful, not rubber-stamp.** Surface the AI's confidence and its reasoning so the human is reviewing a judgment, not just clicking approve. Route only the uncertain cases to humans where you can; reserve scarce expert attention for where it changes the outcome.
- **Design the fallback.** Decide explicitly what happens when the AI is unavailable, slow, or low-confidence — does the work stop, proceed with a default, or escalate? Untested fallbacks are a top source of production incidents.

### Build, pilot, and instrument from day one

Build the redesigned workflow as a contained pilot with real users and real volume — not a demo on cherry-picked inputs. Instrument it before launch: the metrics you will judge it on (cycle time, throughput, quality, cost, adoption) must be wired in from the first day, against the Phase 1 baseline. A pilot you cannot measure is a pilot you cannot defend.

Refer to the [Tooling Landscape](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/04-tooling-landscape.md) for build options, and confirm the underlying data meets the bar in [Track 03: Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md) — redesigns routinely stall because the data the new workflow assumes isn't actually available or clean.

**Phase 2 deliverable:** a redesigned, instrumented workflow running in a controlled pilot with real users; documented human-in-the-loop checkpoints and fallback behavior; and a target-state process map showing what changed from the Phase 1 current state and why.

---

## Phase 3: Change management and rollout (overlapping, weeks 8–16+)

The goal of Phase 3 is adoption — the redesigned workflow becoming how people actually work, not a tool that sits unused while everyone quietly reverts to the old way. This phase is where most of the program's risk lives, and it is the phase most often under-resourced.

### Treat adoption as the hard part, because it is

The base rate for organizational change is sobering. Across fifteen years of McKinsey research on transformations, fewer than one-third succeed at both improving performance and sustaining the gains (McKinsey, *The science behind successful organizational transformations*, 2021) — the empirical backbone behind the familiar "most transformations fail" line (the round 70% figure traces to Kotter). AI does not get a pass on this; it inherits the same adoption physics, plus a layer of fear specific to automation.

That fear is measurable. A 2025 Pew survey found that 52% of U.S. workers were worried about the future impact of AI in the workplace, against just 36% who felt hopeful, and 32% expected it to reduce their job opportunities (Pew Research Center, 2025). You cannot manage that away with a launch email. People who fear a tool will replace them do not adopt it well.

The flip side is that change management is the most reliable lever you have. Prosci's research across more than a decade of data finds that initiatives with excellent change management are **seven times more likely to meet objectives** than those with poor change management — roughly 88% meeting or exceeding objectives versus 13% (Prosci, *Best Practices in Change Management*, 12th ed.). The investment pays for itself.

### Run change management in parallel, not at the end

Start the change effort during Phase 2 build, not after launch. The core moves:

- **Involve the people who do the work in the redesign.** The frontline staff you interviewed in discovery should help shape the new workflow. Co-design converts the most credible potential resisters into advocates and surfaces practical failure modes engineers miss.
- **Be honest and specific about the role change.** Vague reassurance ("AI will augment, not replace you") breeds distrust. Say concretely what the AI takes over, what the human now owns, and how the role changes. The augmentation framing is only credible if the redesign actually reflects it.
- **Invest in reskilling early.** The skills demand is real and large: the World Economic Forum projects that 59% of the global workforce will need training by 2030, and that 39% of workers' core skills will be transformed or outdated over 2025–2030 (WEF, *Future of Jobs Report 2025*). Pair every significant workflow change with the specific capability-building it requires; coordinate with [Track 07: Talent & Capability Building](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/index.md).
- **Close the leadership-perception gap.** Leaders systematically underestimate how much their people are already using AI — McKinsey found 13% of employees use gen AI for at least 30% of their daily work, while the C-suite estimated just 4%, a roughly 3x gap (McKinsey, *Superagency in the Workplace*, 2025). Your workforce is likely further along (and using more shadow tools) than leadership assumes. Build on that existing momentum instead of treating adoption as a standing start.

### Roll out in waves with reinforcement

Expand from pilot to full rollout in waves, not a single cutover. Each wave: train the cohort, run the new workflow alongside support, gather feedback, fix the friction, then expand. Reinforcement matters — adoption decays without it. Make the new way easier than the old way (remove access to the legacy path once a team is live), celebrate the early adopters, and keep a visible feedback channel so problems surface before they become reasons to revert. Broader adoption and culture practices live in [Track 06: AI Adoption & Culture](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/index.md).

**Phase 3 deliverable:** the redesigned workflow adopted by the target population, with documented training, a defined role-change communication, an active feedback loop, and adoption metrics (active users, share of volume running through the new workflow) trending toward target.

---

## Phase 4: Measurement and iteration (continuous, from launch)

The goal of Phase 4 is a decision: scale this workflow, keep fixing it, or kill it — made against instrumented evidence rather than anecdote. Measurement is not a closing report; it is a continuous loop that starts the day the pilot goes live.

### Measure, because most organizations don't

The measurement gap is the quiet killer of optimization programs. McKinsey's 2025 survey found that more than 80% of organizations reported no tangible enterprise-level EBIT impact from gen AI, and fewer than 20% tracked well-defined KPIs for their gen AI initiatives (McKinsey, *The state of AI*, 2025). The two facts are connected: you cannot manage toward an impact you never instrument. Independent surveys echo it — 46% of organizations report having no structured ROI measurement framework at all (Wavestone, *Global AI Survey 2025*), and Deloitte found 41% of organizations struggled to define and measure the impact of their gen AI efforts, with only 16% producing regular value reports for the CFO (Deloitte, *State of Generative AI in the Enterprise*, Q3 2024).

> Fewer than 20% of organizations track well-defined KPIs for their generative-AI initiatives, and more than 80% report no enterprise-level EBIT impact (McKinsey, *The state of AI*, 2025). Those two numbers are not a coincidence — unmeasured value is, in practice, uncaptured value.

When workflows *are* redesigned and measured, the results justify the effort. McKinsey documented a North American telecom that paired gen AI with workflow redesign in customer care and cut total call volume by about 30%, reduced average handle time by more than 25%, and lifted first-call resolution by 10–20 percentage points (McKinsey, *From promising to productive: Real results from gen AI in services*, 2024). And among organizations that do measure, the ROI lands: nearly three-quarters report their most advanced gen AI initiative is meeting or exceeding ROI expectations (Deloitte, *State of Generative AI in the Enterprise*, Q4 2024).

### What to instrument

Measure against the Phase 1 baseline. Four dimensions, plus adoption:

| Dimension | What to instrument | Watch for |
|---|---|---|
| **Cycle time / throughput** | End-to-end time per instance; volume processed per period | Faster steps that don't shorten the end-to-end time (the bottleneck moved, not disappeared) |
| **Quality** | Error rate, rework rate, exception rate, downstream complaint/defect rate | Speed gains paid for with quality loss; AI errors slipping past review |
| **Cost** | Fully loaded cost per instance (labor + AI/compute + tooling) | AI/compute and oversight cost erasing the labor savings |
| **Adoption** | Active users; share of total volume running through the new workflow | High deployment, low usage — the workflow exists but people revert |
| **Outcome / value** | The business metric the workflow ultimately serves (revenue, retention, SLA) | Local optimization that doesn't move the metric that matters |

Two instrumentation disciplines separate credible programs from theatre. **Baseline before you change** — Phase 1 captured this; without it your post-deployment numbers are unanchored. And **measure net, not gross** — the savings that count are after AI/compute costs and the cost of human oversight. A workflow that "saves" twenty hours of labor but adds twenty-five hours of review and a large inference bill is a loss wearing a win's clothing.

### Run the iteration loop and make the kill decision

Review each workflow on a fixed cadence (monthly is reasonable early on). Compare to baseline and target. Then act: where the workflow beats target, scale it to the next population; where it underperforms but the cause is fixable (a redesign flaw, a data gap, a training gap), fix and re-measure; where it has been given a fair run and the value isn't there, **kill it.** The willingness to kill underperformers is a feature, not a failure — it is precisely what the ~5% of organizations capturing real value do that the rest don't. Feed the consolidated results into enterprise value tracking via [Track 08: Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md).

**Phase 4 deliverable:** a live measurement dashboard per workflow (baseline vs. current across the dimensions above), a fixed review cadence, and a documented scale/fix/kill decision for each initiative.

---

## Common failure patterns and how to avoid them

These are the patterns that recur across automation and AI programs. Each one is avoidable; each one is common precisely because the path of least resistance leads straight into it.

**Automating a bad process.** The most expensive mistake. Lift-and-shift automation of an unstandardized, inefficient workflow magnifies the inefficiency (Gates, 1996) and locks it in. *Avoid it:* standardize and redesign before you automate; deprioritize any candidate that isn't yet stable (Phase 1).

**Bolting AI on instead of redesigning.** The data is unambiguous: workflow redesign had the single largest effect on EBIT impact in McKinsey's 2025 study, yet only ~21% of gen-AI users had done it (McKinsey, 2024/2025). Inserting an AI step into the old flow captures a fraction of the available value. *Avoid it:* design the target-state workflow first (Phase 2).

**The pilot that never scales.** The signature failure of the era. Roughly 95% of enterprise gen-AI pilots delivered no measurable P&L impact (MIT NANDA, 2025); Gartner predicted at least 30% of gen-AI projects would be abandoned after proof of concept by end of 2025 (Gartner, 2024); and the share of companies scrapping the majority of their AI initiatives jumped from 17% to 42% year over year (S&P Global Market Intelligence, 2025). Pilots stall because they were never designed to scale, never measured, or never adopted. *Avoid it:* instrument from day one (Phase 2), run real change management (Phase 3), and gate scaling on measured results (Phase 4).

**The scale gap, learned the RPA way.** This is not new. EY observed that 30–50% of initial RPA projects failed (EY, 2016), and Deloitte found only 3% of organizations had scaled RPA to 50+ bots (Deloitte, 2018). The cause then is the cause now: programs that don't standardize processes and don't build the operating discipline to run automations at scale. *Avoid it:* treat the program as a rolling portfolio with governance, not a series of one-off projects.

**Ignoring the people.** Fewer than one-third of transformations succeed (McKinsey, 2021), and over half of workers are worried about AI at work (Pew, 2025). A technically perfect workflow that people fear or resent will not be adopted. *Avoid it:* co-design with frontline staff, communicate role changes honestly, reskill early, and reinforce after launch (Phase 3).

**Flying blind on value.** Fewer than 20% of organizations track well-defined KPIs (McKinsey, 2025) and 46% have no ROI framework (Wavestone, 2025). Without a baseline and net measurement, you cannot tell the wins from the losses, so you scale both. *Avoid it:* baseline in Phase 1, instrument in Phase 2, and measure net value continuously in Phase 4.

---

## What good looks like

A well-run workflow optimization program, a few quarters in, looks like this:

**Discovery is evidence-led.** Workflow selection is driven by documented baselines and value/feasibility scoring — not by whichever use case had the loudest sponsor. For high-volume processes, the selection reflects what the event logs show, not just what people said in interviews.

**Workflows are redesigned, not paved.** Each shipped workflow looks materially different from its predecessor — steps eliminated, handoffs collapsed, checks moved earlier — because the team asked how the work *should* flow given AI, not where to insert a model.

**Humans are in the loop on purpose.** Review checkpoints sit where the stakes justify them, route the uncertain cases to people, and surface the AI's reasoning so review is real. Fallback behavior is defined and tested.

**People adopted the change.** The share of volume running through the new workflow is high and rising, the legacy path has been retired for live teams, and the frontline talks about the new workflow as theirs because they helped design it. Reskilling kept pace with the role changes.

**Every workflow is measured net, against a baseline.** A dashboard shows cycle time, quality, cost, adoption, and the business outcome — before versus now — with AI/compute and oversight costs netted out. The monthly review produces a clear scale/fix/kill decision, and underperformers actually get killed.

**The program runs as a portfolio.** Discovery, build, rollout, and measurement run as a rolling pipeline, with governance and a standard operating rhythm — so the organization is in the ~5% that captures real value rather than the majority whose pilots quietly evaporate.

---

For the conceptual model behind this program, see the [Workflow Optimization Framework](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md). To choose the right degree of automation per step, see [The Four Levels of Workflow AI Integration](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md). For build options, see the [Tooling Landscape](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/04-tooling-landscape.md). To score and rank opportunities, work through the [Workflow Maturity & Opportunity Scoring assessment](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/06-assessment-workflow-maturity-and-opportunity-scoring.md).

## Sources

- McKinsey Global Institute — *A Future That Works: Automation, Employment, and Productivity* — 2017 (https://www.mckinsey.com/featured-insights/digital-disruption/harnessing-automation-for-a-future-that-works)
- McKinsey Global Institute — *The economic potential of generative AI: The next productivity frontier* — 2023 (https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/the-economic-potential-of-generative-ai-the-next-productivity-frontier)
- McKinsey Global Institute — *The Social Economy: Unlocking Value and Productivity Through Social Technologies* — 2012 (https://www.mckinsey.com/industries/technology-media-and-telecommunications/our-insights/the-social-economy)
- Gartner (cited in Process Excellence Network) — *Highlights from Gartner's 2025 Magic Quadrant for Process Mining* — 2025 (https://www.processexcellencenetwork.com/process-mining/articles/highlights-gartners-2025-magic-quadrant-process-mining)
- Deloitte — *Global Intelligent Automation Survey* — 2020 (https://www.deloitte.com/us/en/insights/topics/talent/intelligent-automation-2020-survey-results.html)
- McKinsey & Company (QuantumBlack) — *The state of AI: How organizations are rewiring to capture value* — 2025 (https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai)
- McKinsey & Company (QuantumBlack) — *The state of AI in early 2024: Gen AI adoption spikes and starts to generate value* — 2024 (https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-2024)
- Brynjolfsson, Li & Raymond — *Generative AI at Work* — NBER, 2023 (https://www.nber.org/papers/w31161)
- Dell'Acqua et al. — *Navigating the Jagged Technological Frontier* — Harvard Business School / BCG, 2023 (https://aiinstitute.hbs.edu/navigating-the-jagged-technological-frontier/)
- GitHub — *Research: quantifying GitHub Copilot's impact on developer productivity and happiness* — 2022 (https://github.blog/news-insights/research/research-quantifying-github-copilots-impact-on-developer-productivity-and-happiness/)
- MIT NANDA (MIT Media Lab) — *The GenAI Divide: State of AI in Business 2025* — 2025 (https://fortune.com/2025/08/18/mit-report-95-percent-generative-ai-pilots-at-companies-failing-cfo/)
- McKinsey & Company — *The science behind successful organizational transformations* — 2021 (https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/successful-transformations)
- Pew Research Center — *U.S. Workers Are More Worried Than Hopeful About Future AI Use in the Workplace* — 2025 (https://www.pewresearch.org/social-trends/2025/02/25/u-s-workers-are-more-worried-than-hopeful-about-future-ai-use-in-the-workplace/)
- Prosci — *Best Practices in Change Management* (12th Edition) — 2023 (https://www.prosci.com/blog/the-correlation-between-change-management-and-project-success)
- World Economic Forum — *The Future of Jobs Report 2025* — 2025 (https://www.weforum.org/publications/the-future-of-jobs-report-2025/)
- McKinsey & Company — *Superagency in the Workplace: Empowering People to Unlock AI's Full Potential at Work* — 2025 (https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/superagency-in-the-workplace-empowering-people-to-unlock-ais-full-potential-at-work)
- Wavestone — *Global AI Survey 2025: The paradox of AI adoption* — 2025 (https://www.wavestone.com/en/insight/global-ai-survey-2025-ai-adoption/)
- Deloitte — *The State of Generative AI in the Enterprise: Now Decides Next* (Q3/Wave 3) — 2024 (https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html)
- Deloitte — *The State of Generative AI in the Enterprise: Generating a New Future* (Q4/Wave 4) — 2025 (https://www.prnewswire.com/news-releases/the-path-to-sustainable-generative-ai-value-balances-passion-pragmatism-and-patience-finds-new-deloitte-survey-302355026.html)
- McKinsey & Company — *From promising to productive: Real results from gen AI in services* — 2024 (https://www.mckinsey.com/capabilities/operations/our-insights/from-promising-to-productive-real-results-from-gen-ai-in-services)
- EY (Ernst & Young) — *Get ready for robots: Why planning makes the difference between success and disappointment* — 2016 (https://eyfinancialservicesthoughtgallery.ie/wp-content/uploads/2016/11/ey-get-ready-for-robots.pdf)
- Deloitte — *The robots are ready. Are you? — Deloitte Global RPA Survey* — 2018 (https://www2.deloitte.com/bg/en/pages/technology/articles/deloitte-global-rpa-survey-2018.html)
- Gartner — *Gartner Predicts 30% of Generative AI Projects Will Be Abandoned After Proof of Concept By End of 2025* — 2024 (https://www.gartner.com/en/newsroom/press-releases/2024-07-29-gartner-predicts-30-percent-of-generative-ai-projects-will-be-abandoned-after-proof-of-concept-by-end-of-2025)
- S&P Global Market Intelligence — *Voice of the Enterprise: AI & Machine Learning* — 2025 (https://www.spglobal.com/market-intelligence/en/news-insights/research/ai-experiences-rapid-adoption-but-with-mixed-outcomes-highlights-from-vote-ai-machine-learning)
- Bill Gates (Gates, Myhrvold & Rinearson) — *The Road Ahead* — 1996
