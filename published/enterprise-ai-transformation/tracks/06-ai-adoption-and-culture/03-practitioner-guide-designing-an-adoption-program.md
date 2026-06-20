---
type: Playbook
title: "Practitioner Guide: Designing an Adoption Program"
description: "How to design an AI adoption program from scratch — champions, communication cadence, managing fear and resistance, and measuring adoption progress."
tags: [ai-adoption, practitioner-guide, change-management, playbook]
timestamp: "2026-06-18"
---

## What This Guide Is For

The [AI Adoption Framework](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) makes the case that culture, not capability, is the binding constraint on AI value — and that ~95% of organizations get zero return because tools are deployed but workflows never change ([MIT NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)). This guide is the operational answer: how to actually design and run an adoption program so the human layer keeps pace with the technical rollout.

It is deliberately structured as a sequence — sponsorship before champions, champions before communication, communication and enablement running together, resistance managed throughout, and measurement wired in from day one. The order matters because the most common cause of failed adoption is starting in the middle: buying licenses and announcing training without securing the sponsorship and safety that make either land. The companion [Adoption Maturity Scoring](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/04-assessment-adoption-maturity-scoring.md) assessment is the measurement instrument this guide points to; here we keep metrics light and focus on building the program.

A grounding fact to keep in front of you: BCG's accounting of where AI effort should go is **roughly 10% on algorithms, 20% on technology and data, and 70% on people and process** ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy)). An adoption program is how you spend the 70% deliberately instead of by accident.

---

## Phase 0: Sponsorship and Governance First

Before any champion is named or any training is scheduled, secure active, visible executive sponsorship. This is not a formality — it is the single best-evidenced predictor of change success. Across Prosci's benchmarking studies, **active and visible executive sponsorship has been the top contributor to change success in every study since 1998** ([Prosci, 2023](#ev-prosci-best-practices-2023-sponsorship-top-contributor)), and projects with strong change management overall are far more likely to deliver: **88% of projects with excellent change management met or exceeded objectives, versus 73% with good, 39% with fair, and just 13% with poor change management** ([Prosci, 2023](#ev-prosci-correlation-2023-cm-quality-objectives)).

> **88% vs 13%** — projects with excellent change management meet or exceed objectives nearly seven times as often as those with poor change management ([Prosci, 2023](#ev-prosci-correlation-2023-cm-quality-objectives)).

What "active and visible" requires of the sponsor, concretely:

- **Be reachable.** Prosci found **71% of participants with adequate or better sponsor access met or exceeded objectives, versus only 21% with little or no access** ([Prosci, 2023](#ev-prosci-best-practices-2023-sponsor-access)). A sponsor who appears at the kickoff and then disappears is a non-sponsor.
- **Model the behavior.** A sponsor who does not personally use AI cannot credibly ask anyone else to. Modeling is covered below, but it starts here.
- **Resource the program.** Name an accountable program owner, allocate champion time, and fund enablement — adoption fails when it is everyone's job and no one's budget.

Phase 0 also sets the governance guardrails the program will operate inside: which tools are sanctioned, what data may and may not go into them, and where to get help. This is the handoff point with the governance track — the program should launch on top of a published [AI acceptable-use policy](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-ai-policy-and-acceptable-use.md), not in a policy vacuum. Clarity here is itself an adoption lever: **45% of desk workers report they lack explicit permission or guidelines to use AI** ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-permission-gap)), and that ambiguity is read as disapproval.

---

## Phase 1: Build a Champions Network

Champions are the multiplier that lets a small program team reach an entire workforce. They are respected peers — not necessarily senior, and frequently not in IT — who use AI well, help colleagues locally, and feed real friction back to the program team.

**Who to choose.** Select for behavior and credibility, not title. Good champions are already the people others ask for help, are curious, are vocal about a tool's limits as well as its strengths, and are trusted within their team. The principle that matters most: **champions volunteer, they are not "voluntold."** A reluctant nominee carries none of the peer credibility that makes the role work, and some of the best champions sit well outside IT.

**How many, and how to size the network.** There is no single ratio — and notably, the major workplace-AI publishers decline to publish one, because the right density depends on team structure and tool complexity. A workable planning range used in practice is **one champion per roughly 50–100 users, or about 1–3% of the user base**, scaled up where the work is more varied or the tool more complex. Start small and invited — a single cohort that proves the model — rather than appointing hundreds on day one.

**What they do.** Give the role explicit, bounded responsibilities so it does not become an unfunded burden:

- Run local demos and answer day-to-day "how do I…" questions for their team.
- Hold light-touch office hours or a peer channel where colleagues can ask without judgment.
- Surface recurring friction, good use cases, and failures back to the program team.
- Model open, disclosed AI use — making it normal to say "I used AI for this."

**Support and recognize them.** Budget real time for the role (commonly a few hours a month), give champions early access to new features and advanced training, convene them on a regular cadence (monthly at minimum), and recognize the work visibly. A champions network that is asked to do the work on top of a full job, with no recognition, decays within a quarter.

---

## Phase 2: Communication Strategy and Cadence

Communication is where most fear is either defused or amplified. The two design rules that matter most are about *repetition* and *who delivers which message*.

**Repeat, then repeat again.** People do not absorb a change message on first contact. Prosci's guidance is to **communicate key change messages five to seven times, through multiple channels**, before assuming they have landed ([Prosci, 2023](#ev-prosci-five-steps-2023-repeat-five-to-seven)). A single launch email is not a communication plan.

**Match the message to the messenger.** Employees want different messages from different people: the **business "why" — the case for change — from senior leaders, and the personal "what does this mean for me" from their direct manager** ([Prosci, 2023](#ev-prosci-five-steps-2023-preferred-senders)). This is not interchangeable. A "what's in it for me" message from a distant executive rings hollow; a strategy message from a line manager lacks authority. Managers are the highest-leverage channel for the personal message — Gallup finds **managers account for at least 70% of the variance in team engagement** ([Gallup, 2015](#ev-gallup-state-american-manager-2015-engagement-variance)) — so equip them explicitly rather than assuming the message cascades on its own.

**Address the fear directly, by name.** The framework page documents that the loudest brakes on adoption are fear of job loss and fear of looking incompetent or like a cheat ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-admission-discomfort); [Pew Research Center, 2025](#ev-pew-workers-ai-2025-worried-vs-hopeful)). Communication that ignores those fears reads as tone-deaf and deepens them. Name them: be explicit about what AI is and is not expected to replace, frame AI use as a skill to be proud of rather than a shortcut to hide, and make leadership's own use visible so disclosure feels safe.

A simple cadence that works: a leadership-delivered "why" at launch; manager-delivered "what this means for your role" within the first two weeks; recurring champion-led tips and wins; and a steady drumbeat of internally-sourced success stories. Keep the channel open in both directions — a place to ask questions and report what isn't working is part of the communication plan, not separate from it.

---

## Phase 3: Training and Enablement

The enablement gap is stark and is directly costing adoption: **30% of desk workers have had no AI training at all, and 61% have spent fewer than five hours learning to use AI** ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-training-hours)). Yet only **39% of AI users say they have received AI training from their employer**, even as **66% of leaders say they would not hire someone without AI skills** ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-training-hiring)) — a contradiction the program has to resolve.

The payoff for closing the gap is large. Slack's data shows **workers trained on AI are up to 19 times as likely to say it improves their productivity, and well-trained workers are roughly 7 times as likely to trust AI tools** ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-training-payoff)). Training is not overhead; it is the conversion mechanism from access to use.

What effective enablement looks like in practice:

- **Role-based, not generic.** A finance analyst, a customer-support agent, and a marketer need different use cases. Generic "intro to AI" sessions teach the tool; role-based sessions teach the job-with-the-tool, which is what changes behavior.
- **Prompt and judgment skills, not just features.** The hard part of generative AI is directing it and evaluating its output — the calibrated-trust skill from the framework page. Teach how to spot a wrong answer, not only how to ask for one.
- **Just-in-time, recurring formats.** Short office hours, a peer Q&A channel, and a searchable library of vetted prompts beat a one-time mandatory course that is forgotten by the next week. This is where the champions network does much of the real work.
- **Communities of practice.** A standing forum where people share what worked normalizes use and surfaces the use cases worth scaling.

---

## Phase 4: Managing Fear and Resistance

Resistance is not an obstacle to route around; it is information about what the program has not yet addressed. Three patterns need explicit handling.

**Job-security anxiety.** This is widespread and partly rational — **65% of US employees report being anxious about AI replacing their jobs** ([EY, 2023](#ev-ey-ai-anxiety-2023-job-replacement)), and the figure rises inside organizations that have already adopted AI ([Gallup, 2026](#ev-gallup-rising-ai-adoption-2026-job-elimination)). The only credible response is honesty about intent paired with visible investment in people: if the goal is augmentation, say so and prove it by funding reskilling (the [talent and capability track](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/index.md) is the partner here); if roles will genuinely change, say that too. Vague reassurance that no one believes is worse than candor.

**Hidden use and the fear of judgment.** Nearly half of workers would be uncomfortable admitting AI use to their manager ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-admission-discomfort)). The fix is psychological safety, built deliberately: leaders disclosing their own AI use and their own AI mistakes, managers explicitly inviting it, and recognition for good disclosed use. The framework page's empirical anchor applies directly — disclosure comfort tracks a **67% higher likelihood of actually using AI** ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-disclosure-comfort)).

**Shadow AI.** Suppressed demand does not vanish; it goes underground. **78% of AI users already bring their own tools** ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-byoai)), about half use unsanctioned "shadow AI" ([Software AG, 2024](#ev-software-ag-shadow-ai-2024-half)), and **prohibition makes covert use worse, not better — inappropriate use such as putting sensitive data into public tools runs to 67% of employees where AI is banned versus 33% where it is not** ([KPMG, 2025](#ev-kpmg-trust-ai-2025-ban-vs-noban-misuse)). The program's job is to *channel* this demand: provide sanctioned tools that are genuinely good enough that no one needs a workaround, publish clear acceptable-use rules, and treat existing shadow users as a ready-made pool of champions rather than offenders.

Underlying all three is psychological safety as defined in the team-effectiveness literature — "a shared belief that the team is safe for interpersonal risk taking" ([Edmondson, 1999](#ev-edmondson-1999-psychological-safety); [Google re:Work, 2015](#ev-google-project-aristotle-2015-psych-safety)). Without it, fear is simply driven out of sight, where it cannot be addressed.

---

## Phase 5: Measuring Progress

Measurement is built in from the start, not bolted on at review time — and it distinguishes leading indicators (which predict adoption) from lagging ones (which confirm value).

| Type | What to track | Why |
|---|---|---|
| **Leading** | Training completion, champion coverage, % of target roles with explicit permission, sentiment/disclosure comfort, weekly active users | These move first and tell you whether the program is working while there is still time to adjust |
| **Lagging** | Habitual (daily/weekly) use in core workflows, workflow redesigns shipped, productivity and quality outcomes, value realized | These confirm whether adoption converted to value — but lag by quarters |

Two cautions. First, do not mistake access metrics (licenses provisioned, first-week logins) for adoption metrics (sustained use, workflow change) — that confusion is the original sin the framework page warns against. Second, instrument sentiment, not just usage: a rising usage number alongside falling disclosure comfort signals adoption being driven underground, which is fragile and risky.

For the full measurement instrument — maturity dimensions, a 1–5 scoring ladder, engagement benchmarks, and resistance mapping — use the companion [Adoption Maturity Scoring](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/04-assessment-adoption-maturity-scoring.md) assessment.

---

## A Note on "Most Change Efforts Fail"

You will hear that "70% of change initiatives fail." Treat it with suspicion. The figure has no sound empirical basis — it traces to an unscientific estimate about business re-engineering in the early 1990s and has been repeated uncited ever since, with no original study behind it ([Hughes, 2011](#ev-hughes-change-failure-myth-2011-no-evidence)). The defensible, sourced point is the inverse and the more useful one: change is hard, but *change management quality is controllable and decisive* — the difference between 88% and 13% success rates above is a function of how well the program is run ([Prosci, 2023](#ev-prosci-correlation-2023-cm-quality-objectives)). Design the program well and the odds are not fixed against you.

---

## Checklist

- [ ] **Sponsorship secured** — a named, active, reachable executive sponsor who personally uses AI and has funded the program.
- [ ] **Governance guardrails published** — sanctioned tools and an acceptable-use policy in place before launch.
- [ ] **Champions network seeded** — a small, volunteer, credible first cohort with bounded responsibilities, allocated time, and recognition.
- [ ] **Communication plan** — repeated 5–7 times across channels; "why" from leaders, "what it means for me" from managers; fears named explicitly.
- [ ] **Role-based enablement** — job-specific use cases, prompt-and-judgment skills, just-in-time formats, communities of practice.
- [ ] **Resistance plan** — honest job-security messaging, deliberate psychological safety, shadow AI channeled into sanctioned tools.
- [ ] **Metrics wired in** — leading and lagging indicators defined from day one; sentiment instrumented alongside usage; baselined via the [maturity assessment](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/04-assessment-adoption-maturity-scoring.md).

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **MIT Project NANDA — *The GenAI Divide: State of AI in Business 2025*, 2025.** Just 5% of integrated AI pilots are extracting millions in value, while the vast majority remain stuck with no measurable P&L impact. [View source](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf){#ev-mit-nanda-genai-divide-2025-no-pl-impact} · verified 2026-06-20 · ⚠ secondary mirror
- **BCG — *Where's the Value in AI?*, 2024.** AI leaders follow the rule of putting 10% of their resources into algorithms, 20% into technology and data, and 70% into people and processes. [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-2024-ten-twenty-seventy} · verified 2026-06-20 · primary
- **Prosci — *Best Practices in Change Management*, 2023.** Active and visible sponsorship has been identified as the greatest contributor to change-management success in every Prosci benchmarking study since 1998. [View source](https://www.prosci.com/resources/articles/change-management-best-practices){#ev-prosci-best-practices-2023-sponsorship-top-contributor} · verified 2026-06-20 · ⚠ secondary mirror
- **Prosci — *The Correlation Between Change Management and Project Success*, 2023.** Percent meeting or exceeding project objectives: excellent change management 88%, good 73%, fair 39%, poor 13% (roughly seven times more likely with excellent vs poor change management). [View source](https://www.prosci.com/resources/articles/change-management-correlation-to-project-success){#ev-prosci-correlation-2023-cm-quality-objectives} · verified 2026-06-20 · primary
- **Prosci — *Best Practices in Change Management*, 2023.** 71% of participants with adequate or more than adequate sponsor access met or exceeded project objectives, compared with only 21% of those with little or no access. [View source](https://www.prosci.com/resources/articles/change-management-best-practices){#ev-prosci-best-practices-2023-sponsor-access} · verified 2026-06-20 · ⚠ secondary mirror
- **Slack Workforce Lab — *Fall 2024 Workforce Index*, 2024.** Close to half of workers (45%) do not have explicit permission to use AI; 30% say they have had no AI training at all, including no self-directed learning or experimentation. [View source](https://slack.com/blog/news/the-fall-2024-workforce-index-shows-executives-and-employees-investing-in-ai-but-uncertainty-holding-back-adoption){#ev-slack-workforce-index-2024-permission-gap} · verified 2026-06-20 · primary
- **Prosci — *Five Steps to Better Change Management Communication*, 2023.** The Prosci methodology recommends communicating key messages five to seven times, through multiple channels, to be effective. [View source](https://www.prosci.com/resources/articles/change-management-communication){#ev-prosci-five-steps-2023-repeat-five-to-seven} · verified 2026-06-20 · ⚠ secondary mirror
- **Prosci — *Five Steps to Better Change Management Communication*, 2023.** Business leaders are the preferred senders of organizational/business messages; an employee's immediate supervisor is the preferred sender of personal-impact messages. [View source](https://www.prosci.com/resources/articles/change-management-communication){#ev-prosci-five-steps-2023-preferred-senders} · verified 2026-06-20 · primary
- **Gallup — *State of the American Manager*, 2015.** Managers account for at least 70% of the variance in employee engagement scores across business units. [View source](https://www.gallup.com/services/182138/state-american-manager.aspx){#ev-gallup-state-american-manager-2015-engagement-variance} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *Fall 2024 Workforce Index*, 2024.** Nearly half (48%) of all desk workers would be uncomfortable admitting to their manager that they used AI for common workplace tasks; reasons include feeling like using AI is cheating (47%), fear of being seen as less competent (46%), and fear of being seen as lazy (46%). [View source](https://slack.com/blog/news/the-fall-2024-workforce-index-shows-executives-and-employees-investing-in-ai-but-uncertainty-holding-back-adoption){#ev-slack-workforce-index-2024-admission-discomfort} · verified 2026-06-20 · primary
- **Pew Research Center — *U.S. Workers Are More Worried Than Hopeful About Future AI Use in the Workplace*, 2025.** About half of workers (52%) say they are worried about the future impact of AI use in the workplace; 36% say they feel hopeful; about a third (32%) say it will lead to fewer opportunities for them. [View source](https://www.pewresearch.org/social-trends/2025/02/25/u-s-workers-are-more-worried-than-hopeful-about-future-ai-use-in-the-workplace/){#ev-pew-workers-ai-2025-worried-vs-hopeful} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *Fall 2024 Workforce Index*, 2024.** The majority of desk workers (61%) have spent less than five hours learning how to use AI. [View source](https://slack.com/blog/news/the-fall-2024-workforce-index-shows-executives-and-employees-investing-in-ai-but-uncertainty-holding-back-adoption){#ev-slack-workforce-index-2024-training-hours} · verified 2026-06-20 · primary
- **Microsoft & LinkedIn — *2024 Work Trend Index Annual Report*, 2024.** Only 39% of people who use AI at work have received AI training from their company; 66% of leaders say they would not hire someone without AI skills. [View source](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part){#ev-microsoft-work-trend-2024-training-hiring} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *Workforce Index (June 2024)*, 2024.** Workers trained to use AI are up to 19x as likely to report that AI improves their productivity; desk workers well trained in AI are 7x as likely to trust AI tools to assist with work tasks as those lacking AI training. [View source](https://slack.com/blog/news/the-workforce-index-june-2024){#ev-slack-workforce-index-2024-training-payoff} · verified 2026-06-20 · primary
- **EY — *EY research shows most US employees feel AI anxiety*, 2023.** About two-thirds (65%) say they are anxious about AI replacing their job. [View source](https://www.ey.com/en_us/newsroom/2023/12/ey-research-shows-most-us-employees-feel-ai-anxiety){#ev-ey-ai-anxiety-2023-job-replacement} · verified 2026-06-20 · primary
- **Gallup — *Rising AI Adoption Spurs Workforce Changes*, 2026.** 18% of all U.S. employees say it is very or somewhat likely their job will be eliminated within the next five years due to AI or automation; among employees in organizations that have adopted AI, that share rises to 23%. [View source](https://www.gallup.com/workplace/704225/rising-adoption-spurs-workforce-changes.aspx){#ev-gallup-rising-ai-adoption-2026-job-elimination} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *Fall 2024 Workforce Index*, 2024.** Those who are comfortable sharing that they used AI for work tasks are 67% more likely to have used AI for work than those who would not be comfortable admitting AI use. [View source](https://slack.com/blog/news/the-fall-2024-workforce-index-shows-executives-and-employees-investing-in-ai-but-uncertainty-holding-back-adoption){#ev-slack-workforce-index-2024-disclosure-comfort} · verified 2026-06-20 · primary
- **Microsoft & LinkedIn — *2024 Work Trend Index Annual Report*, 2024.** 78% of AI users are bringing their own AI tools to work (BYOAI). [View source](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part){#ev-microsoft-work-trend-2024-byoai} · verified 2026-06-20 · primary
- **Software AG — *Shadow AI study*, 2024.** Half of all employees are shadow-AI users, relying on unsanctioned or ad-hoc AI tools their company did not provide. [View source](https://newscenter.softwareag.com/en/news-stories/press-releases/2024/1022-half-of-all-employees-use-shadow-ai.html){#ev-software-ag-shadow-ai-2024-half} · verified 2026-06-20 · ⚠ secondary mirror
- **KPMG & University of Melbourne — *Trust, Attitudes and Use of AI: A Global Study 2025*, 2025.** Using AI in ways that contravene organizational policies is most common among employees who report their organization has banned generative AI (67%), compared with those in organizations without such policies (33%). [View source](https://kpmg.com/xx/en/our-insights/ai-and-technology/trust-attitudes-and-use-of-ai.html){#ev-kpmg-trust-ai-2025-ban-vs-noban-misuse} · verified 2026-06-20 · primary
- **Amy C. Edmondson — *Psychological Safety and Learning Behavior in Work Teams (Administrative Science Quarterly, 44(2), 350-383)*, 1999.** A shared belief held by members of a team that the team is safe for interpersonal risk taking; team psychological safety is associated with learning behavior, which mediates between psychological safety and team performance. [View source](https://doi.org/10.2307/2666999){#ev-edmondson-1999-psychological-safety} · verified 2026-06-20 · primary
- **Google re:Work — *Project Aristotle: Understand Team Effectiveness*, 2015.** Psychological safety was far and away the most important of the five dynamics we found; it is the underpinning of the other four. [View source](https://rework.withgoogle.com/guides/understanding-team-effectiveness/){#ev-google-project-aristotle-2015-psych-safety} · verified 2026-06-20 · primary
- **Mark Hughes — *Do 70 Per Cent of All Organizational Change Initiatives Really Fail? (Journal of Change Management, 11(4))*, 2011.** Although a popular narrative of 70% organizational-change failure exists, there is no valid and reliable empirical evidence to support such a narrative. [View source](https://doi.org/10.1080/14697017.2011.630506){#ev-hughes-change-failure-myth-2011-no-evidence} · verified 2026-06-20 · primary
