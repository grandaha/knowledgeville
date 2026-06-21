---
type: Reference
title: Stakeholder Communication Templates
description: "Ready-to-use communication templates for boards, employees, IT and data functions, external stakeholders, and program status updates."
tags: [program-management, communication, templates, reference]
timestamp: "2026-06-18"
---

An AI transformation succeeds or fails on the same eight interdependent tracks described in the [Framework Architecture](/enterprise-ai-transformation/framework-architecture.md) — but every one of those tracks runs on a substrate of communication. The investment case the board signs off on, the augmentation promise employees decide whether to believe, the guardrails IT is asked to enforce, the responsible-AI posture customers judge you by: each is a message before it is a result. And the evidence is that communication is where transformations are most often lost. Towers Watson's long-running study found that companies with the highest communication effectiveness delivered a **57% higher total return to shareholders** over five years than those communicating least effectively, and were **3.5 times more likely to significantly outperform their industry peers** ([Towers Watson, 2013–2014](#ev-towers-watson-comm-roi-2013-2014-tsr-outperformance)). This page is a templates library: for each of five audiences, a short note on what they need to hear and the failure to avoid, then a ready-to-use template with `[bracketed placeholders]` you fill in.

> **The central principle: match the message to the messenger, and say the hard thing first.** Employees want the business "why" from senior leaders and the personal "what does this mean for me" from their own manager — these are not interchangeable, and a "what's in it for you" message from a distant executive rings as hollow as a strategy message from a line manager ([Prosci, 2023](#ev-prosci-five-steps-2023-preferred-senders)). And because people hear a change message through the filter of their own anxiety, key messages must be repeated **five to seven times across multiple channels** before they land ([Prosci, 2023](#ev-prosci-five-steps-2023-repeat-five-to-seven)). None of these templates is a one-and-done.

The templates below are original work and free to adapt; the statistics in the framing prose are cited to their primary sources so you can verify or update them.

---

## Board and executive leadership

The board needs a clear-eyed investment case paired with an honest risk posture — not hype. The credibility problem is concrete: **88% of organizations now use AI in at least one function, but only 39% report any EBIT impact from it, and roughly 6% attribute more than 5% of EBIT to AI** ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-adoption); [McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-ebit-any); [McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-high-performers)); BCG similarly finds **60% of companies capture no material value at scale** ([BCG, 2025](#ev-bcg-value-gap-2025-distribution)). A board has heard the promises and seen the gap. The failure to avoid is the unanchored ask — a funding request untethered from evidence. Tie the case to your own [integrated assessment](/enterprise-ai-transformation/running-the-program/integrated-assessment.md) results and name the binding constraint you intend to fund, so the ask is a diagnosis, not a wish. Boards are increasingly equipped to engage: AI is now off the back burner at most companies, with only **31% of boards saying AI is not on their agenda, down from 45% a year earlier** ([Deloitte, 2025](#ev-deloitte-governance-ai-2025-board-agenda)).

```
TO:       Board / Executive Committee
FROM:     [Program Sponsor], [Title]
RE:       AI Transformation — Investment Case and Risk Posture, [Quarter/Year]
DECISION REQUESTED: Approve [$amount] for [time horizon] against the
                    constraint identified below.

1. WHERE WE ARE (evidence, not intent)
   Our integrated assessment scored the eight tracks on a 1–5 ladder.
   Current state: [e.g., "Foundation strong (Data 4, Platform 4),
   Execution lagging (Adoption 2, Talent 2)"].
   The binding constraint — the lowest track throttling everything
   downstream — is [Track X]. We are funding that, not the loudest
   or most visible layer.

2. THE INVESTMENT CASE
   Outcome we are buying: [specific business outcome, e.g., "cut
   [process] cycle time [X%], freeing [$Y] of capacity"].
   What [$amount] funds: [the constraint-relieving work].
   How we will know it worked: [the leading + lagging metrics from
   Measurement track 08], reported to this body every [cadence].
   What we are NOT funding yet, and why: [the tracks we are
   deliberately staging behind their dependencies].

3. RISK POSTURE (what could go wrong, and our controls)
   | Risk                        | Likelihood | Our control                       |
   | --------------------------- | ---------- | --------------------------------- |
   | [Data/privacy exposure]     | [L/M/H]    | [governance guardrail / policy]   |
   | [Model error in [process]]  | [L/M/H]    | [human-in-the-loop / review path] |
   | [Regulatory / compliance]   | [L/M/H]    | [oversight, see governance track] |
   | [Adoption fails to stick]   | [L/M/H]    | [adoption program, sentiment KPI] |
   Governance and oversight are covered by [our AI governance track];
   [committee/role] owns AI risk on behalf of the board.

4. THE ASK
   Approve [$amount]; next decision gate at [date], when [metric]
   will tell us whether to scale, hold, or stop.
```

---

## Employees and people managers

Employees need the truth about job security, framed honestly — not vague reassurance no one believes. The anxiety is real and well-evidenced: **65% of US employees say they are anxious about AI replacing their job** ([EY, 2023](#ev-ey-ai-anxiety-2023-job-replacement)), and that fear does not subside with familiarity — Gallup found the share of employees who think their job will be eliminated within five years **rises from 18% overall to 23% inside organizations that have actually adopted AI** ([Gallup, 2026](#ev-gallup-rising-ai-adoption-2026-job-elimination)). A second, quieter fear compounds it: **48% of desk workers would be uncomfortable telling their manager they use AI**, fearing it will be seen as cheating or as a sign they are less competent ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-admission-discomfort)). The failure to avoid is the cheerful non-answer — "AI will free you up for higher-value work!" — delivered without saying what happens to the work AI absorbs. Address job security by name, commit to augmentation concretely (back it with the [talent and capability track](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/index.md)), and make leaders' own AI use visible so disclosure feels safe. Deliver the "why" from a senior leader and the "what this means for your role" from the direct manager.

```
[FROM A SENIOR LEADER — the "why," org-wide]

Subject: How we're approaching AI — and what it means for your job

Team,

I want to be direct about something on a lot of minds. We are adopting
AI across [function/company], and I know the unspoken question is:
is this about replacing people?

Here is our honest answer. Our intent is augmentation, not headcount
reduction: we want AI to absorb [the repetitive, low-judgment parts of
the work — e.g., drafting, data entry, first-pass analysis] so you can
spend more time on [the parts that need human judgment]. Concretely,
that commitment looks like [reskilling investment / redeployment policy
/ what we will and won't do]. Where roles genuinely change, we will say
so plainly and support the transition — I would rather tell you a hard
truth than a comfortable fiction.

Two things I want to make normal here:
  1. Using AI is a skill to build, not a shortcut to hide. I use it
     for [specific example], and I get plenty wrong while I learn.
  2. The sanctioned tools and the rules for them are at [link]. If
     you're unsure whether something is allowed, ask — asking is
     never the wrong move.

Your manager will follow up on what this means for your specific role.
Bring them your questions, including the uncomfortable ones.

— [Name]
```

```
[FROM A PEOPLE MANAGER — the "what this means for YOU," to a team]

Subject: AI on our team — what changes, what doesn't

Hi all,

Following [leader]'s note, here's what AI means for us specifically.

What's changing: [the tasks AI will take on in our work].
What's NOT changing: [the responsibilities that remain yours; the
headcount commitment as it applies to this team].
What I'm asking of you: try [tool] on [specific use case] this
[timeframe]. You will not be judged for using it — or for finding
it doesn't help yet. Tell me which.
Support you'll get: [training / champion / office hours], and time
carved out to learn — this is part of the job, not extra.

My door is open for the question behind the question. If you're
worried about your role, say so to me directly and I'll be straight
with you.

— [Manager]
```

---

## IT and data functions

IT and data teams need a precise statement of what is being asked of them and the authority to deliver it — not an open-ended mandate to "support AI." They are the Foundation layer of the framework (platform and data readiness), and the binding-constraint principle bites hardest here: nothing automates reliably on bad data, and there is nowhere to build without a coherent platform. The failure to avoid is the demand-without-guardrails request that turns IT into a bottleneck and breeds shadow AI — **78% of AI users already bring their own tools to work** ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-byoai)), so suppressed demand does not vanish, it goes underground. The fix is to give IT and data a scoped charter, sanctioned tooling, and a published acceptable-use policy from the [AI governance and risk track](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/index.md) to enforce against.

```
TO:    IT & Data Platform leads
FROM:  [Program Sponsor]
RE:    AI Transformation — what we're asking of you, and what you get

WHAT WE'RE ASKING (scoped, not open-ended):
  Platform:   Stand up [sanctioned model access / shared AI platform]
              so teams build on paved roads, not point solutions.
              Target: [capability] available to [user group] by [date].
  Data:       Make [named priority domains] AI-ready — governed,
              accessible, with lineage. NOT "fix all data"; only the
              domains the funded use cases depend on: [list].
  Guardrails: Enforce the acceptable-use policy [link] — what data may
              and may not enter which tools, access controls, logging.

WHAT YOU GET (so this isn't an unfunded mandate):
  - Authority: a published policy to enforce against, not case-by-case
    judgment calls. Escalation path for exceptions: [route].
  - Scope discipline: use cases are sequenced behind their data and
    platform dependencies, so you are not asked to support everything
    at once. The funded priorities are [list].
  - A channel for shadow AI: we will surface and sanction the tools
    people already use rather than only policing them — treat current
    unsanctioned users as a pipeline, not offenders.
  - Resourcing: [headcount / budget / vendor support].

WHAT WE NEED BACK FROM YOU:
  - A readiness read on [domains]: what's fit for purpose, what isn't.
  - The platform constraints we should design the rollout around.
  - Flags on any request that outruns the guardrails — early.

Owner / DRI: [name]. First checkpoint: [date].
```

---

## External stakeholders and customers

Customers and external stakeholders need transparency about where and how you use AI, and evidence of a responsible-AI posture. The demand is unambiguous: **76% of Americans say it is important to be able to tell whether content was made by AI or by people** ([Pew Research Center, 2025](#ev-pew-ai-detection-2025-importance-of-disclosure)), and **86% of consumers say AI-generated content should be disclosed** ([Meltwater & YouGov, 2026](#ev-meltwater-yougov-2026-disclosure-expectation)). Trust is the scarce resource — only **46% of people globally are willing to trust AI systems** ([KPMG & University of Melbourne, 2025](#ev-kpmg-trust-ai-2025-willing-to-trust)) — but transparency is the lever that moves it: **83% say they would be more willing to trust an AI system when assurance mechanisms such as human oversight and responsible-AI policies are in place** ([KPMG & University of Melbourne, 2025](#ev-kpmg-trust-ai-2025-assurance-mechanisms-trust)). The failure to avoid is silent deployment — using AI in customer-facing interactions without disclosure, then losing trust when it surfaces. Lead with disclosure and back it with a concrete responsible-AI posture rather than a slogan.

```
[CUSTOMER-FACING — responsible-AI statement / FAQ entry]

How we use AI

We use AI to [specific, honest uses — e.g., "draft responses our
team reviews," "surface relevant answers faster," "personalize
recommendations"]. We tell you when you're interacting with AI:
[where the disclosure appears — chat labels, content tags, etc.].

Our commitments to you:
  - Disclosure: you'll always be able to tell when content or a
    response was generated with AI.
  - Human oversight: [where a person reviews / where you can reach
    a human — "ask for a person at any point and you'll get one"].
  - Your data: we [do / do not] use your data to train models;
    [what we do and don't do with it]. Details: [privacy link].
  - Accountability: our responsible-AI standards are governed by
    [team/policy], and you can raise a concern at [channel].

We'd rather earn your trust by being clear than surprise you later.
[Link to fuller responsible-AI policy.]
```

---

## Program status updates

A recurring status update keeps every audience oriented and the program honest with itself. Sponsors and stakeholders need to know what shipped, what it was worth, what's next, and — most importantly — what decisions they owe the program. The failure to avoid is the activity report: pages of "we held workshops and provisioned licenses" that confuse access metrics with value. Anchor every update in outcomes from the [Measurement and Value Realization track](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md), and let the evidence pace the next investment, as the [program architecture](/enterprise-ai-transformation/running-the-program/program-architecture.md) prescribes — ship something small, measure it, let it pull the next move. Use a fixed structure every period so readers can scan it in two minutes.

```
AI TRANSFORMATION — STATUS UPDATE
Period: [date range]   ·   RAG: [Green / Amber / Red]   ·   DRI: [name]

WHAT SHIPPED (outcomes, not activity)
  - [Capability/workflow that went live, to whom]
  - [What changed for users — not "trained 40 people" but "40 people
    now use [tool] in [workflow]"]

WHAT IT'S WORTH (evidence from Measurement track 08)
  | Metric                    | Baseline | Now    | Target |
  | ------------------------- | -------- | ------ | ------ |
  | [Leading: weekly active]  | [ ]      | [ ]    | [ ]    |
  | [Lagging: cycle time / $] | [ ]      | [ ]    | [ ]    |
  Sentiment check: [adoption / disclosure-comfort signal] — flag if
  usage is rising while sentiment falls (adoption going underground).

WHAT'S NEXT (staggered by dependency)
  - [Next funded move and why now — which constraint it relieves]
  - [What we're deliberately holding behind its dependency]

DECISIONS NEEDED (the point of the update)
  - [Decision], owner: [who], needed by: [date], because: [impact
    of not deciding].
  - [Blocker requiring escalation].

RISKS / CHANGES SINCE LAST PERIOD
  - [New or changed risk + the control].
```

---

## Key Takeaways

- **Communication is a track, not a footnote.** The highest-communication companies returned **57% more to shareholders** and were **3.5x more likely to outperform peers** ([Towers Watson, 2013–2014](#ev-towers-watson-comm-roi-2013-2014-tsr-outperformance)) — treat comms as load-bearing infrastructure for all eight tracks.
- **Match message to messenger, and repeat.** The business "why" comes from senior leaders, the personal "what this means for me" from direct managers, and key messages need **five to seven repetitions across channels** to land ([Prosci, 2023](#ev-prosci-five-steps-2023-repeat-five-to-seven)).
- **Name job-security fear honestly.** With **65% of employees anxious about AI taking their jobs** ([EY, 2023](#ev-ey-ai-anxiety-2023-job-replacement)) — anxiety that *rises* after adoption ([Gallup, 2026](#ev-gallup-rising-ai-adoption-2026-job-elimination)) — augmentation has to be a concrete, funded commitment, not a slogan, and disclosed use must be made safe given **48% are uncomfortable admitting AI use to their manager** ([Slack Workforce Lab, 2024](#ev-slack-workforce-index-2024-admission-discomfort)).
- **Give IT guardrails, not an open mandate.** A scoped charter plus a published acceptable-use policy channels the **78% who bring their own tools** ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-byoai)) into sanctioned paths instead of shadow AI.
- **Disclose to customers — transparency builds trust.** With **86% wanting AI-generated content disclosed** ([Meltwater & YouGov, 2026](#ev-meltwater-yougov-2026-disclosure-expectation)) and **83% more willing to trust AI when assurance mechanisms exist** ([KPMG & University of Melbourne, 2025](#ev-kpmg-trust-ai-2025-assurance-mechanisms-trust)), lead with disclosure and a real responsible-AI posture.
- **Report outcomes, not activity.** Anchor status updates in Measurement-track evidence, surface the decisions the program is owed, and let proven value pace the next investment.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Towers Watson — *Change and Communication ROI Study (2013-2014)*, 2013-2014.** Companies with the highest communication effectiveness delivered a 57% higher total return to shareholders over a five-year period than those communicating least effectively, and were 3.5 times more likely to significantly outperform their industry peers. [View source](https://magneto.net.au/wp-content/uploads/2018/07/2013-2014-change-and-communication-roi-study-towers-watson.pdf){#ev-towers-watson-comm-roi-2013-2014-tsr-outperformance} · verified 2026-06-20 · ⚠ secondary mirror
- **Prosci — *Five Steps to Better Change Management Communication*, 2023.** Business leaders are the preferred senders of organizational/business messages; an employee's immediate supervisor is the preferred sender of personal-impact messages. [View source](https://www.prosci.com/resources/articles/change-management-communication){#ev-prosci-five-steps-2023-preferred-senders} · verified 2026-06-20 · primary
- **Prosci — *Five Steps to Better Change Management Communication*, 2023.** The Prosci methodology recommends communicating key messages five to seven times, through multiple channels, to be effective. [View source](https://www.prosci.com/resources/articles/change-management-communication){#ev-prosci-five-steps-2023-repeat-five-to-seven} · verified 2026-06-20 · ⚠ secondary mirror
- **McKinsey — *The State of AI*, 2025.** 88% of respondents report regular AI use in at least one business function, compared with 78% a year ago. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-adoption} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI*, 2025.** About 39% of organizations report any enterprise-level EBIT impact from AI; most of those say less than 5% of EBIT is attributable to AI use. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-ebit-any} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI*, 2025.** Respondents who attribute EBIT impact of 5 percent or more to AI use and say their organization has seen significant value from AI — about 6 percent of respondents — are defined as AI high performers. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-high-performers} · verified 2026-06-20 · primary
- **BCG — *The Widening AI Value Gap*, 2025.** Only about 5% of companies (the 'future-built') are generating value at scale, while 60% of companies are laggards with little or no value; 35% are in between. [View source](https://media-publications.bcg.com/The-Widening-AI-Value-Gap-Sept-2025.pdf){#ev-bcg-value-gap-2025-distribution} · verified 2026-06-20 · primary
- **Deloitte — *Governance of AI: A critical imperative for today's boards (2nd edition)*, 2025.** Nearly a third of respondents (31%) say AI is not on the board agenda, down from 45% in the previous survey. [View source](https://www.deloitte.com/global/en/issues/trust/progress-on-ai-in-the-boardroom-but-room-to-accelerate.html){#ev-deloitte-governance-ai-2025-board-agenda} · verified 2026-06-20 · primary
- **EY — *EY research shows most US employees feel AI anxiety*, 2023.** About two-thirds (65%) say they are anxious about AI replacing their job. [View source](https://www.ey.com/en_us/newsroom/2023/12/ey-research-shows-most-us-employees-feel-ai-anxiety){#ev-ey-ai-anxiety-2023-job-replacement} · verified 2026-06-20 · primary
- **Gallup — *Rising AI Adoption Spurs Workforce Changes*, 2026.** 18% of all U.S. employees say it is very or somewhat likely their job will be eliminated within the next five years due to AI or automation; among employees in organizations that have adopted AI, that share rises to 23%. [View source](https://www.gallup.com/workplace/704225/rising-adoption-spurs-workforce-changes.aspx){#ev-gallup-rising-ai-adoption-2026-job-elimination} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *Fall 2024 Workforce Index*, 2024.** Nearly half (48%) of all desk workers would be uncomfortable admitting to their manager that they used AI for common workplace tasks; reasons include feeling like using AI is cheating (47%), fear of being seen as less competent (46%), and fear of being seen as lazy (46%). [View source](https://slack.com/blog/news/the-fall-2024-workforce-index-shows-executives-and-employees-investing-in-ai-but-uncertainty-holding-back-adoption){#ev-slack-workforce-index-2024-admission-discomfort} · verified 2026-06-20 · primary
- **Microsoft & LinkedIn — *2024 Work Trend Index Annual Report*, 2024.** 78% of AI users are bringing their own AI tools to work (BYOAI). [View source](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part){#ev-microsoft-work-trend-2024-byoai} · verified 2026-06-20 · primary
- **Pew Research Center — *How Americans View AI and Its Impact on People and Society*, 2025.** 76% of Americans say it is extremely or very important to be able to tell whether pictures, videos and text were made by AI or by people. [View source](https://www.pewresearch.org/science/2025/09/17/how-americans-view-ai-and-its-impact-on-people-and-society/){#ev-pew-ai-detection-2025-importance-of-disclosure} · verified 2026-06-20 · primary
- **Meltwater & YouGov — *Trust in the Age of Generative AI*, 2026.** 86% of consumers say AI-generated content should be disclosed. [View source](https://www.meltwater.com/en/about/press-releases/consumer-perception-of-generative-ai){#ev-meltwater-yougov-2026-disclosure-expectation} · verified 2026-06-20 · primary
- **KPMG & University of Melbourne — *Trust, Attitudes and Use of AI: A Global Study 2025*, 2025.** Only 46% of people globally are willing to trust AI systems. [View source](https://kpmg.com/xx/en/our-insights/ai-and-technology/trust-attitudes-and-use-of-ai.html){#ev-kpmg-trust-ai-2025-willing-to-trust} · verified 2026-06-20 · primary
- **KPMG & University of Melbourne — *Trust, Attitudes and Use of AI: A Global Study 2025*, 2025.** 83% say they would be more willing to trust an AI system when assurance mechanisms such as human oversight and responsible-AI policies are in place (confirmed in the Australia country snapshot; the global figure should be confirmed). [View source](https://kpmg.com/xx/en/our-insights/ai-and-technology/trust-attitudes-and-use-of-ai.html){#ev-kpmg-trust-ai-2025-assurance-mechanisms-trust} · verified 2026-06-20 · ⚠ secondary mirror
