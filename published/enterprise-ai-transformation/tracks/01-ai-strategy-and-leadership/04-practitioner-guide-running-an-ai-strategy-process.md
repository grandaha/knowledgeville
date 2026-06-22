---
type: Playbook
title: "Practitioner Guide: Running an AI Strategy Process"
description: A five-phase process for running an enterprise AI strategy from scratch — securing sponsorship, aligning stakeholders, prioritizing use cases, deciding build/buy/partner and resourcing, and building a governed 12-month roadmap.
tags: [ai-strategy, roadmap, prioritization, operating-model, change-management]
timestamp: "2026-06-15"
---

## The Problem

Most organizations do not lack AI ambition. They lack a *process* for turning ambition into a funded, sequenced, governed plan — so the ambition scatters into disconnected pilots that never compound into value.

> Only **25%** of AI initiatives have delivered the ROI organizations expected over the last few years, and only **16%** have scaled enterprise-wide ([IBM Institute for Business Value, 2025](#ev-ibm-ibv-ceo-2025-enterprise-scale))

[The core framework](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/02-ai-strategy-framework.md) defines *what* a good AI strategy contains — a value thesis, a funded portfolio, the decisions only leadership can make, and the governance above the program. This guide is the *how*: the repeatable process that produces that strategy, run as five sequential phases over roughly a quarter.

| Phase | Produces |
| --- | --- |
| **1 — Frame & Sponsor** | A chartered mandate with a named executive sponsor |
| **2 — Assess & Align** | A current-state baseline + alignment on priority domains |
| **3 — Generate & Prioritize Use Cases** | A ranked, funded shortlist with owners and metrics |
| **4 — Decide Posture & Resource** | Per-initiative build/buy/partner, funding, and redesign plans |
| **5 — Roadmap & Govern** | A sequenced 12-month roadmap, operating model, and cadence |

Each phase has a clear output that becomes the next phase's input. Do not start a phase until the prior one has produced its artifact — with one deliberate exception: use-case ideation (early Phase 3) can begin in parallel with late Phase 2 as the priority domains firm up.

---

## Phase 1 — Frame & Sponsor

The goal of this phase is singular: secure the mandate before anyone runs a single piece of analysis. Strategy work that begins without an explicit charter drifts, stalls, or gets quietly overruled. Fix the authority first.

Run four activities, in order:

- **Win an explicit executive mandate.** Get a named decision-maker to authorize the effort on the record — not a hallway nod, but a documented commitment of time, budget, and air cover.
- **Name a single accountable senior sponsor.** One executive owns this, not a steering committee. Diffuse ownership is no ownership.
- **Define scope and the business question.** State plainly what the strategy must answer and where its boundaries sit. Anchor it to a business outcome, not to a technology you want to deploy.
- **Set success criteria up front.** Agree on what a good answer looks like before the analysis can bias the target.

The sponsor is the load-bearing element here — an active, visible owner who shows up through the engagement, not a kickoff cameo who delegates and disappears.

> Active and visible executive sponsorship ranks as the **#1 contributor** to change-program success ([Prosci, 2023](#ev-prosci-best-practices-2023-sponsorship-top-contributor)); projects with extremely effective sponsorship are nearly **3.5x** more likely to meet or exceed objectives than those with very ineffective sponsorship ([Prosci, 2023](#ev-prosci-top-contributors-2023-sponsorship-multiplier))

Who's involved: the CEO or a C-suite executive as accountable sponsor, the strategy lead who will run the process, and the budget owner. Keep the circle small. The sponsor's authority — what they can decide, fund, and override — should be explicit; the core framework defines the decision rights they hold.

Pin down the business question hard enough to resist FOMO. Pressure to move fast pushes organizations to commit capital before they understand the value, and the result is fragmented investment.

> **64%** of CEOs say the risk of falling behind drives investment in AI before they have a clear understanding of the value it brings; **50%** say the pace of investment has left their organization with disconnected, piecemeal technology ([IBM Institute for Business Value, 2025](#ev-ibm-ibv-ceo-2025-invest-before-value))

**What the chartered mandate contains:**
- **Named executive sponsor and decision rights** — the specific person accountable, and what they can fund, approve, override, or veto without escalation.
- **The business question** the strategy must answer, stated in one sentence.
- **In-scope and out-of-scope boundaries** — which domains, functions, or processes the effort will and will not examine.
- **Success criteria** — how a good answer will be judged, and what makes a recommendation credible to this sponsor.
- **Budget and time envelope** for the strategy effort itself (not the initiatives it may propose).
- **Core team and sponsor cadence** — who does the work, and how often the sponsor reviews and unblocks it.
- **Decision date** — when the strategy is due and the choice will be made.

It fits on one page, and the sponsor signs it before any analysis begins.

**Output:** a chartered mandate — a short document naming the executive sponsor, the scope and business question, and the success criteria, signed off by the sponsor.

**Avoid:** a passive sponsor or committee-by-everyone ownership, and FOMO-driven scoping that funds activity before the value is understood. If no single executive will put their name to it, stop here — the strategy is not yet sponsored.

---

## Phase 2 — Assess & Align

The purpose of this phase is to establish one honest, shared read of where you stand — and to align leadership on where AI actually matters to *this* business — before anyone brainstorms a single use case. Skip it, and you generate use cases against a fantasy of your own capabilities and a vague notion of value. The alignment produced here is not a precursor to the real work. It is the deliverable.

Treat this as an organizational exercise, not a technical one. The economics bear it out:

> Across leading AI programs, roughly **70%** of the effort and impact comes from people and process change, **20%** from technology and data, and **10%** from algorithms ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy))

Key activities:

- **Baseline current-state maturity.** Assess your AI, data, talent, and operating-model readiness against a structured rubric. Score it with [the strategic readiness scoring diagnostic](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/05-assessment-strategic-readiness-scoring.md) so the read is defensible, not anecdotal.
- **Convene the full stakeholder set.** Bring business-unit leaders, IT, data, and risk into the same room and drive them to a shared view of reality. Disagreement surfaced here is cheaper than disagreement surfaced in production.
- **Name the priority domains.** Identify the two to four areas where AI changes this company's economics — cost structure, growth, or risk — not where the technology is most interesting. Define "where it matters" against [the eight-track model](/enterprise-ai-transformation/framework-architecture.md) so the choice is grounded in your actual operating system.
- **Capture the value-thesis inputs.** Record the assumptions, constraints, and economic logic behind each priority domain to feed the next phase.

Who's involved: the executive sponsor chairs; business-unit leaders own the value call; IT, data, and risk validate feasibility and exposure. The sponsor's job is to force genuine cross-functional agreement, not to ratify a slide.

> In a study drawing on interviews with experienced AI practitioners, misunderstood or miscommunicated intent and purpose — a stakeholder-alignment gap — was the single most common cause of AI project failure ([RAND, 2024](#ev-rand-ai-projects-fail-2024-failure-rate))

**Running the alignment session:** Convene a half-day facilitated workshop with business, IT, data, and risk owners in one room; each function pre-reads the maturity baseline so the session starts from shared facts, not introductions. Working from a candidate list, the group ranks domains live on a value-vs-readiness wall, placing each one by hand and arguing the placement. Force a cut to 2–4 priorities before anyone leaves. Log disagreements verbatim rather than smoothing them over — unresolved tension is a finding, not a failure.

**Each priority domain gets a one-pager capturing:**
- The business problem and the economics it changes
- Why now — the trigger making this the moment to act
- The data and capability it depends on
- The rough value hypothesis (directional, not precise)
- The main risk or constraint that could stall it
- The named executive who owns the domain

**Output:** a current-state baseline plus documented stakeholder alignment on two to four priority domains, with the inputs to the value thesis captured.

**Avoid:** letting IT own this phase alone, or aligning on exciting technology instead of business value — the most common path to a stalled program.

---

## Phase 3 — Generate & Prioritize Use Cases

This is the methodological heart of the process: convert strategic ambition into a ranked, funded shortlist. Most programs fail here — they generate enthusiasm, then fund everything. Your job is to do the opposite: surface broadly, then cut hard.

Run structured ideation against the priority domains from Phase 2, not against the latest vendor demo. Frame every candidate as a business outcome ("cut claims cycle time 40%"), never a technology ("deploy a chatbot"). Then prioritize in two passes.  <!-- noev: illustrative outcome-framing example, not a sourced statistic -->

Start with the **value × feasibility 2×2**. Plot each candidate on business value (vertical) against feasibility (horizontal). Four quadrants drive four decisions: **quick wins** (high value, high feasibility) — do now; **big bets** (high value, low feasibility) — sequence later, once enablers mature; **fill-ins** (low value, high feasibility) — defer; **drop** (low value, low feasibility) — kill on sight. The 2×2 is for fast triage and executive alignment, not the final cut.

For the shortlist, use a **weighted scoring model**. Score each surviving use case 1–5 on every criterion, multiply by the weight, sum, rank, and draw a funding cutoff line.

| Criterion | Weight |
| --- | --- |
| Business value | 30% |
| Technical feasibility | 20% |
| Data readiness | 15% |
| Strategic fit | 15% |
| Risk & compliance | 10% |
| Time-to-value | 10% |

Tune the weights to maturity: early-stage organizations weight feasibility and data readiness higher to bank early proof; mature organizations weight strategic value higher to fund transformation. Define the criteria so they don't overlap and inflate scores — *Business value* is P&L impact; *Strategic fit* is alignment with the value thesis and priority domains. Every use case above the cutoff must carry a **named owner** — a single accountable executive, not a committee — and a **pre-agreed success metric** set before a line of code is written. No owner, no metric, no funding.

Who's involved: business-unit leaders own value scores and outcomes; a central AI/data team owns feasibility and data-readiness scores — and critically, the team that wants to build a use case never scores its own feasibility; finance validates value claims against the P&L; the steering committee ratifies the cutoff. Build/buy/partner posture and the value thesis behind each score are defined in the core framework.

Focus is the differentiator, not breadth.

> AI leaders prioritize on average **3.5** use cases versus **6.1** for other companies, and anticipate **2.1x** greater ROI on their AI initiatives ([BCG, 2025](#ev-bcg-ai-radar-2025-focus-and-roi))
> Fewer than **5%** of S&P 500 companies pursue a focused ("bimodal") AI strategy, but those that do see **2x** the revenue of their peers and outpace them on total shareholder return by **5.4 percentage points** ([PwC, 2026](#ev-pwc-concentrated-bets-2026-bimodal-premium))

**Worked example.** Score two candidates, normalize each to a 0–100 scale (a perfect 5 on every criterion = 100), and apply a fund-if-≥70 cutoff.

| Use case | Bus. value (30%) | Tech. feasibility (20%) | Data readiness (15%) | Strategic fit (15%) | Risk & compliance (10%) | Time-to-value (10%) | **Weighted total** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Claims triage assistant | 5 | 3 | 4 | 5 | 3 | 4 | **83** |
| Marketing copy generator | 2 | 5 | 4 | 2 | 4 | 4 | **66** |

Claims triage clears the cutoff at **83** (30 + 12 + 12 + 15 + 6 + 8), driven by top business value and strategic fit. The copy generator scores high on feasibility, data readiness, and speed but lands at **66** (12 + 20 + 12 + 6 + 8 + 8) — below 70 — because weak business value and strategic fit dominate the weighting. Fund claims triage; defer the copy generator.

**Output:** a ranked, funded shortlist of use cases, each with a named owner and a pre-agreed success metric.

**Avoid:** boiling the ocean with too many pilots; choosing tech-first instead of value-first; funding demos instead of P&L impact; and letting the team that wants to build a use case grade its own feasibility.

---

## Phase 4 — Decide Posture & Resource

With a funded shortlist in hand, leadership converts intent into commitment. The purpose of this phase is to make the resourcing and posture calls for each surviving initiative — and to design the work around the bet, not the tool around the work.

Run three activities, initiative by initiative.

First, **decide build vs. buy vs. partner** against the value thesis. A commodity capability gets bought; a source of differentiation gets built; a capability you need fast but can't yet staff gets partnered. Test each posture against the thesis, not against vendor enthusiasm. The build/buy/partner decision and the risk-appetite calls are leadership decision rights defined in the core framework — make them explicitly, not by default.

Second, **commit real funding and a named owner.** Not a placeholder budget and a steering committee — actual dollars and one accountable executive per initiative, with a funded path from pilot to production. An initiative without a production budget is a science project.

Third — and this is where the value actually lives — **plan the workflow redesign around each bet.** Map how the work gets done today, then redesign it around the new capability. The tool is the easy part; the returns come from reshaping roles, handoffs, and decision points.

> Only about **21%** of organizations using generative AI have fundamentally redesigned at least some workflows — and workflow redesign is the factor most correlated with bottom-line (EBIT) impact ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-workflow-redesign))
> Companies that have fully modernized to AI-led processes (**16%** in 2024, up from **9%** in 2023) achieve **2.5x** higher revenue growth, **2.4x** greater productivity, and **3.3x** greater success scaling generative AI ([Accenture, 2024](#ev-accenture-ai-led-processes-2024-adoption-and-multipliers))

Who's involved: the executive sponsor and initiative owners make the calls; finance commits the funding; process owners and frontline operators co-design the redesign; technology leadership validates the posture.

**Each funded initiative gets a one-page resourcing brief:**
- **Posture:** build / buy / partner — one line tying the choice to the value thesis (e.g., "Buy: the capability is commodity; speed-to-value beats differentiation").
- **Budget & source:** the committed amount and the budget line it's drawn from (a named cost center, not "TBD").
- **Accountable owner:** one named person who owns the outcome — not a committee, not a function.
- **Workflow redesign:** current-state flow vs. redesigned flow — the roles, handoffs, and decision points that change, and who absorbs the change.
- **Pilot→production gate:** the explicit criteria that release production funding (e.g., "accuracy holds across two cycles; operators accept output without rework").
- **Success metric & target:** the one number that defines success, with its target value.
- **Top risk & mitigation:** the failure most likely to kill value, and the concrete countermeasure.

A use case that cannot name its production gate is not ready to fund.

**Output:** a per-initiative resourcing plan — posture (build/buy/partner), committed funding with a named owner, and a workflow-redesign plan — for every item on the funded shortlist.

**Avoid:** treating AI as a tool bolt-on with no process redesign, or approving initiatives with no funded path from pilot to production. Both produce pilots that demo well and change nothing.

---

## Phase 5 — Roadmap & Govern

This phase converts the funded shortlist into a sequenced, time-bound plan and stands up the operating model that will run it. The purpose is to make the strategy executable and self-correcting: leadership leaves with a roadmap they can resource, an org design that decides who builds and governs AI, and a cadence that forces the portfolio to respond to evidence.

**Part 1 — The 12-month roadmap.** Sequence the shortlist along a dependency-aware path. Front-load foundational and enabling work — data pipelines, the AI platform, governance guardrails, and talent — because nothing scales without it. Run two or three quick wins in parallel to generate proof and momentum while the foundations are laid. Then graduate from point solutions toward end-to-end process transformation, where the value concentrates. Treat the roadmap as a living instrument: re-sequence it as foundations land and use cases prove out.

A sample 12-month shape:

| Quarter | Focus | Example moves |
| --- | --- | --- |
| Q1 | Foundations + 2 quick wins | Stand up the AI platform, data access, and governance guardrails; ship two high-feasibility wins |
| Q2 | Prove & instrument | Move the quick wins into production; baseline value, adoption, and risk metrics |
| Q3 | Scale winners + start a big bet | Expand proven wins to more teams; launch one ambitious, longer-horizon initiative |
| Q4 | Transform & prune | Redesign one end-to-end process around AI; retire initiatives that underperform |

**Part 2 — The operating model.** Choose how AI is organized. The right answer depends on maturity, regulation, and scaling ambition.

| Pattern | How it works | Best for |
| --- | --- | --- |
| **Centralized (Center of Excellence)** | Concentrates scarce talent and governance in one team | Fastest to production; early-stage or regulated |
| **Federated (hub-and-spoke)** | Central standards + shared platform; business units execute | Scaling across multiple business units |
| **Decentralized** | Business-unit-owned teams, own tooling | Maximum local speed; high AI maturity only |

Default to centralized early, then federate as demand and capability grow. The evidence favors holding the center.

> About **70%** of institutions with highly centralized AI operating models have put use cases into production, compared with only about **30%** of those with a fully decentralized approach ([McKinsey, 2024](#ev-mckinsey-banking-operating-model-2024-centralized-production))
> In high-maturity organizations, almost **60%** of leaders have centralized their AI strategy, governance, data, and infrastructure ([Gartner, 2025](#ev-gartner-ai-maturity-2025-centralized-strategy))

Finally, set success metrics and a standing re-direction cadence. Define a small set of value, adoption, and risk metrics per initiative; the metrics and the feedback loop that feeds re-direction live in [Track 08, Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md). Then schedule a quarterly leadership review that inspects evidence, kills or doubles down, and reallocates the portfolio.

**The quarterly re-direction review covers:**
- Value, adoption, and risk metrics versus targets, per initiative
- What to kill and what to double down on
- Reallocation of budget and talent to where signal is strongest
- New candidates promoted in from the backlog
- Foundational gaps blocking next quarter's moves

> **45%** of leaders in high-maturity organizations keep AI initiatives in production for three years or more ([Gartner, 2025](#ev-gartner-ai-maturity-2025-three-year-longevity))

Who's involved: the chief AI officer or transformation lead owns the roadmap; business-unit leaders commit delivery capacity; the data, platform, and risk leads own the enabling tracks; the sponsor chairs the cadence.

**Output:** a sequenced 12-month roadmap, a chosen operating model, a defined success-metric set, and a governance and re-direction cadence on the calendar.

**Avoid:** freezing the roadmap as a static slide; decentralizing before central standards and production capability exist; or running no cadence, so the strategy is set once and quietly drifts.

---

## Common Pitfalls

The failure modes of each phase share a family resemblance: they substitute activity for the disciplined decisions the process exists to force.

> **Over 40%** of agentic AI projects will be canceled by the end of 2027, due to escalating costs, unclear business value, or inadequate risk controls ([Gartner, 2025](#ev-gartner-agentic-ai-2025-project-cancellations))

- **Skipping the mandate.** Running the process without a single accountable sponsor — the strongest predictor of failure.
- **Aligning on technology, not value.** Letting the interesting tech, or the loudest function, set the agenda instead of the business economics.
- **Boiling the ocean.** Funding many shallow pilots instead of a few deep bets — the opposite of what leaders do.
- **Self-scored feasibility.** Letting the team that wants to build a use case grade its own difficulty.
- **Bolting AI onto unchanged work.** Deploying tools without redesigning the workflow around them, where the actual value lives.
- **No funded path to production.** Approving pilots with no budget line to cross from proof of concept into scaled operations.
- **The static roadmap.** Producing a plan once and never re-sequencing it as evidence arrives — the strategy drifts and dies quietly.

---

## Readiness Checklist

- [ ] A single, named, active executive sponsor owns the strategy — not a committee
- [ ] A chartered mandate states the scope, the business question, and success criteria
- [ ] A current-state baseline of AI/data/talent/operating-model maturity exists and is scored, not anecdotal
- [ ] Business, IT, data, and risk are aligned on two to four priority domains where AI changes the economics
- [ ] Use cases were generated as business outcomes, not technologies
- [ ] A prioritization method (value × feasibility, then weighted scoring) produced a ranked shortlist with a funding cutoff
- [ ] Every funded use case has a named owner and a pre-agreed success metric
- [ ] Build/buy/partner posture is decided per initiative against the value thesis
- [ ] Each funded bet has committed funding and a workflow-redesign plan, not just a tool
- [ ] A 12-month roadmap front-loads foundational work and quick wins, and is treated as living
- [ ] An operating model (centralized / federated / decentralized) is chosen to fit current maturity
- [ ] A standing re-direction cadence reviews evidence and reallocates the portfolio

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **IBM Institute for Business Value — *2025 CEO Study (CEOs Double Down on AI While Navigating Enterprise Hurdles)*, 2025.** only 25% of AI initiatives have delivered expected ROI over the last few years, and only 16% have scaled enterprise wide. [View source](https://newsroom.ibm.com/2025-05-06-ibm-study-ceos-double-down-on-ai-while-navigating-enterprise-hurdles){#ev-ibm-ibv-ceo-2025-enterprise-scale} · verified 2026-06-20 · primary
- **Prosci — *Best Practices in Change Management*, 2023.** Active and visible sponsorship has been identified as the greatest contributor to change-management success in every Prosci benchmarking study since 1998. [View source](https://www.prosci.com/resources/articles/change-management-best-practices){#ev-prosci-best-practices-2023-sponsorship-top-contributor} · verified 2026-06-20 · ⚠ secondary mirror
- **Prosci — *Top Contributors to Success*, 2023.** with extremely effective sponsorship, projects were almost 3.5 times more likely to meet or exceed project objectives than projects with very ineffective sponsorship. [View source](https://www.prosci.com/resources/articles/change-management-best-practices){#ev-prosci-top-contributors-2023-sponsorship-multiplier} · verified 2026-06-21 · ⚠ secondary mirror
- **IBM Institute for Business Value — *2025 CEO Study (CEOs Double Down on AI While Navigating Enterprise Hurdles)*, 2025.** 64% of CEOs surveyed acknowledge that the risk of falling behind drives investment in some technologies before they have a clear understanding of the value they bring; half (50%) acknowledge that the pace of recent investments has left their organization with disconnected, piecemeal technology. [View source](https://newsroom.ibm.com/2025-05-06-ibm-study-ceos-double-down-on-ai-while-navigating-enterprise-hurdles){#ev-ibm-ibv-ceo-2025-invest-before-value} · verified 2026-06-21 · primary
- **BCG — *Where's the Value in AI?*, 2024.** AI leaders follow the rule of putting 10% of their resources into algorithms, 20% into technology and data, and 70% into people and processes. [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-2024-ten-twenty-seventy} · verified 2026-06-20 · primary
- **RAND — *The Root Causes of Failure for Artificial Intelligence Projects and How They Can Succeed*, 2024.** By some estimates more than 80 percent of AI projects fail, twice the rate of failure for information technology projects that do not involve AI. [View source](https://www.rand.org/pubs/research_reports/RRA2680-1.html){#ev-rand-ai-projects-fail-2024-failure-rate} · verified 2026-06-20 · primary
- **BCG — *AI Radar 2025: From Potential to Profit - Closing the AI Impact Gap*, 2025.** Leading companies focus on depth over breadth, prioritizing an average of 3.5 use cases, compared with 6.1 use cases for other companies; these companies anticipate generating 2.1 times greater ROI on their AI initiatives than their peers. [View source](https://www.bcg.com/publications/2025/closing-the-ai-impact-gap){#ev-bcg-ai-radar-2025-focus-and-roi} · verified 2026-06-21 · ⚠ secondary mirror
- **PwC — *AI transformation: Why focused (concentrated) bets outperform*, 2026.** fewer than 5% of S&P 500 companies are adopting a bimodal AI transformation strategy; those that do see twice the revenue of their peers, and their total shareholder returns are outpacing their peers by 5.4 percentage points. [View source](https://www.pwc.com/us/en/services/ai/ai-transformation-concentrated-bets.html){#ev-pwc-concentrated-bets-2026-bimodal-premium} · verified 2026-06-21 · ⚠ secondary mirror
- **McKinsey — *The State of AI*, 2025.** 21% of respondents reporting gen AI use say their organizations have fundamentally redesigned at least one workflow; redesigning workflows has the biggest effect on an organization's ability to see EBIT impact from gen AI. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-workflow-redesign} · verified 2026-06-20 · primary
- **Accenture — *Reinventing Enterprise Operations with Gen AI*, 2024.** the number of companies that have fully modernized, AI-led processes has nearly doubled from 9% in 2023 to 16% in 2024; these organizations achieve 2.5x higher revenue growth, 2.4x greater productivity and 3.3x greater success at scaling generative AI use cases. [View source](https://newsroom.accenture.com/news/2024/new-accenture-research-finds-that-companies-with-ai-led-processes-outperform-peers){#ev-accenture-ai-led-processes-2024-adoption-and-multipliers} · verified 2026-06-21 · primary
- **McKinsey — *Scaling gen AI in banking: Choosing the best operating model*, 2024.** About 70 percent of banks and other institutions with highly centralized gen AI operating models have progressed to putting gen AI use cases into production, compared with only about 30 percent of those with a fully decentralized approach. [View source](https://www.mckinsey.com/industries/financial-services/our-insights/scaling-gen-ai-in-banking-choosing-the-best-operating-model){#ev-mckinsey-banking-operating-model-2024-centralized-production} · verified 2026-06-21 · ⚠ secondary mirror
- **Gartner — *Gartner Survey on Organizations With High AI Maturity*, 2025.** In high-maturity organizations, almost 60% of leaders said they have centralized their AI strategy, governance, data and infrastructure capabilities to increase consistency and efficiency. [View source](https://www.gartner.com/en/newsroom/press-releases/2025-06-30-gartner-survey-finds-forty-five-percent-of-organizations-with-high-artificial-intelligence-maturity-keep-artificial-intelligence-projects-operational-for-at-least-three-years){#ev-gartner-ai-maturity-2025-centralized-strategy} · verified 2026-06-21 · ⚠ secondary mirror
- **Gartner — *Gartner Survey on Organizations With High AI Maturity*, 2025.** 45% of organizations with high AI maturity keep their AI projects operational for at least three years. [View source](https://www.gartner.com/en/newsroom/press-releases/2025-06-30-gartner-survey-finds-forty-five-percent-of-organizations-with-high-artificial-intelligence-maturity-keep-artificial-intelligence-projects-operational-for-at-least-three-years){#ev-gartner-ai-maturity-2025-three-year-longevity} · verified 2026-06-21 · ⚠ secondary mirror
- **Gartner — *Gartner Predicts Over 40% of Agentic AI Projects Will Be Canceled by End of 2027*, 2025.** Over 40% of agentic AI projects will be canceled by the end of 2027, due to escalating costs, unclear business value or inadequate risk controls. [View source](https://www.gartner.com/en/newsroom/press-releases/2025-06-25-gartner-predicts-over-40-percent-of-agentic-ai-projects-will-be-canceled-by-end-of-2027){#ev-gartner-agentic-ai-2025-project-cancellations} · verified 2026-06-21 · ⚠ secondary mirror
