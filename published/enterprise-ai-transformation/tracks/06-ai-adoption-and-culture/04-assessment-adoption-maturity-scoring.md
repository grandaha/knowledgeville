---
type: Playbook
title: "Assessment: Adoption Maturity Scoring"
description: "A scoring assessment for AI adoption maturity — utilization and engagement, cultural readiness, leadership modeling, and resistance mapping."
tags: [ai-adoption, assessment, maturity-scoring, playbook]
timestamp: "2026-06-18"
---

## What This Is For

This assessment tells you where your organization actually stands on AI adoption — not how many licenses you bought, but how deeply and safely AI is used. It is the measurement companion to the [AI Adoption Framework](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) (the argument) and the [Designing an Adoption Program](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/03-practitioner-guide-designing-an-adoption-program.md) guide (the how-to). Score yourself before designing a program, to find the binding constraint; score again on a cadence, to see whether it is moving.

The reason a dedicated assessment is needed is the gap the framework documents: access is not adoption. As of early 2024 **only 32% of desk workers had tried AI for work — two-thirds had not — and just 15% strongly agreed they had the training to use it effectively** ([Slack, 2024](#ev-slack-workforce-index-2024-tried-ai)). Even where AI is used, regular use trails far behind trial: in 2025 about **60% of desk workers used AI at least occasionally, but only around 40% weekly and 20% daily** ([Slack, 2025](#ev-slack-new-ai-advantage-2025-usage-frequency)). A maturity score that counts seats would call this success; a score that counts habitual, safe, workflow-integrated use tells the truth.

This page gives you six scoring dimensions, a 1–5 maturity ladder for each, the metrics that feed them, a resistance-mapping overlay, and a method for interpreting the result.

---

## How to Use It

1. **Score each of the six dimensions 1–5** using the ladders below, evidenced by the metrics in the next section — not by impression.
2. **Plot a profile, not an average.** A single low dimension is a bottleneck even when the mean looks healthy. Use the radar/profile to find it.
3. **Overlay the resistance map** to see *where* in the workforce adoption is stuck.
4. **Interpret the pattern** (final section) to choose the next intervention, then point fixes at the relevant phase of the [adoption program guide](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/03-practitioner-guide-designing-an-adoption-program.md).

The five-level structure follows established maturity-model convention — the same Initial → Managed → Defined → Quantitatively Managed → Optimizing progression as CMMI ([CMMI Institute, ISACA](#ev-cmmi-maturity-levels-five-stage)) — so a score is comparable to how the organization already thinks about other capabilities.

---

## The Six Dimensions

| # | Dimension | The question it answers |
|---|---|---|
| D1 | Tool Utilization & Engagement | Are people actually using it — deeply, broadly, and habitually? |
| D2 | Cultural Readiness | Is it safe to experiment, and is trust in AI calibrated? |
| D3 | Leadership Modeling & Sponsorship | Do leaders visibly use AI and actively sponsor adoption? |
| D4 | Enablement & Skills | Are people trained and supported to use AI well? |
| D5 | Governance & Acceptable-Use Clarity | Do people know what is allowed, with sanctioned tools that suffice? |
| D6 | Trust & Verification Practices | Are AI outputs verified appropriately — neither blindly trusted nor reflexively dismissed? |

---

## The 1–5 Maturity Ladder

### D1 — Tool Utilization & Engagement

| Level | What it looks like |
| --- | --- |
| 1 | Licenses provisioned but little real use; no usage tracking; activation well below ~30%. |
| 2 | Activation rising but engagement shallow; daily-active/monthly-active (DAU/MAU) stickiness in the low single digits; use concentrated in a few enthusiasts. |
| 3 | Majority of target users activated; weekly use common in target roles; DAU/MAU approaching ~20%. |
| 4 | Habitual daily use across most target roles; DAU/MAU around the ~31% B2B-SaaS benchmark; breadth across functions. |
| 5 | AI embedded in core workflows; usage tracked and tied to outcomes; sustained retention rather than novelty spikes. |

### D2 — Cultural Readiness (psychological safety, experimentation, trust)

| Level | What it looks like |
| --- | --- |
| 1 | Fear dominates; AI errors are punished; experimentation absent; deep distrust of outputs. |
| 2 | Pockets of curiosity; experimentation tolerated informally but unsafe to admit failure. |
| 3 | Teams openly discuss AI use; failures treated as learning; calibrated trust beginning to form. |
| 4 | Psychological safety high; experimentation is normal and expected; trust calibrated to task risk. |
| 5 | Continuous, open experimentation is the norm; sharing wins *and* failures is routine across teams. |

### D3 — Leadership Modeling & Sponsorship

| Level | What it looks like |
| --- | --- |
| 1 | No visible sponsor; leaders do not use AI themselves. |
| 2 | Verbal support only; no modeling, no resourcing. |
| 3 | A named sponsor exists; some leaders visibly use AI. |
| 4 | Active, visible, reachable sponsorship; leaders model use and remove barriers. |
| 5 | Sponsorship sustained and cascaded through management; leaders coach adoption and disclose their own AI mistakes. |

### D4 — Enablement & Skills

| Level | What it looks like |
| --- | --- |
| 1 | No training; entirely self-taught. |
| 2 | Ad hoc resources; a minority trained; under five hours of learning is typical. |
| 3 | Formal, role-based onboarding for target roles; prompt-and-judgment skills taught. |
| 4 | Continuous enablement: champions network, office hours, just-in-time support, communities of practice. |
| 5 | Skills measured, refreshed, and adapted as capabilities change; enablement keeps pace with the tools. |

### D5 — Governance & Acceptable-Use Clarity

| Level | What it looks like |
| --- | --- |
| 1 | No policy; high shadow-AI exposure; people guess at what is allowed. |
| 2 | A blanket ban or silence — which drives covert use rather than preventing it. |
| 3 | A published acceptable-use policy exists; sanctioned tools are available. |
| 4 | Clear data-handling rules; sanctioned tools cover real needs; shadow AI is low. |
| 5 | Governance enables rather than blocks; monitored and reviewed; demand is met by sanctioned tools. |

### D6 — Trust & Verification Practices

| Level | What it looks like |
| --- | --- |
| 1 | Outputs either blindly accepted or reflexively dismissed; no shared norms. |
| 2 | Verification is ad hoc and personal; over- and under-trust both common. |
| 3 | Basic human-in-the-loop expectations exist for higher-risk uses. |
| 4 | Verification habits are explicit and matched to task risk; people know when to check. |
| 5 | Calibrated trust is cultural: AI relied on where reliable, verified where weak, and the difference is taught. |

---

## Tool Utilization & Engagement Metrics (D1)

Score D1 on evidence, using product-analytics measures rather than seat counts:

- **Activation rate** — share of provisioned users who have completed a meaningful first action, not merely logged in ([Amplitude, 2025](#ev-amplitude-product-adoption-metrics-activation)).
- **DAU/MAU stickiness** — daily-active over monthly-active users, the standard embeddedness proxy. Useful reference points: B2B SaaS sits around **31%**, with **25–35% considered broadly healthy** ([Mixpanel, 2026](#ev-mixpanel-mau-benchmarks-2026-b2b-stickiness)).
- **Breadth** — percentage of *target* roles with any regular use, to catch adoption that is real but confined to one team.
- **Retention** — 30- and 90-day sustained use, which separates habit from a novelty spike. (Daily use grew rapidly through this period — Slack measured daily AI use up 233% in the six months to mid-2025, versus November 2024 — so trend matters as much as level ([Slack, 2025](#ev-slack-new-ai-advantage-2025-daily-use-growth)).)
- **License waste** — provisioned-but-inactive seats. Across SaaS generally, organizations actively use only about **49% of provisioned licenses** ([Zylo, 2024](#ev-zylo-saas-management-index-2024-license-utilization)); AI rollouts are not exempt, and the unused half is both wasted spend and a false adoption signal.

A useful framing: the daily users are where value concentrates. Slack found **daily AI users were markedly more likely to report "very good" productivity, focus, and job satisfaction** than occasional users ([Slack, 2025](#ev-slack-new-ai-advantage-2025-daily-user-outcomes)) — which is why D1 rewards depth and habit, not breadth of access alone.

---

## Cultural Readiness Indicators (D2)

Culture is scored from signals, not vibes:

- **Psychological-safety survey** — adapt Edmondson's validated items; psychological safety is the strongest enabler of the team learning behavior that experimentation requires ([Edmondson, 1999](#ev-edmondson-1999-psychological-safety)), and was the top dynamic of effective teams in Google's large internal study ([Google, 2015](#ev-google-project-aristotle-2015-psych-safety)).
- **Disclosure comfort** — whether people will admit AI use to a manager. This is a leading indicator of real use: those comfortable disclosing are **67% more likely to have used AI for work** ([Slack, 2024](#ev-slack-workforce-index-2024-disclosure-comfort)).
- **Experimentation throughput** — count of shared experiments, prompts contributed, wins and failures posted. Low throughput with high usage signals adoption being driven underground.
- **Trust disposition** — calibrated against a wary baseline: only **46% of people globally are willing to trust AI** ([KPMG, 2025](#ev-kpmg-trust-ai-2025-willing-to-trust)), so neither blanket enthusiasm nor blanket suspicion is the target.

---

## Resistance Mapping

Adoption maturity is not uniform across a workforce, so a single score hides the real problem. Overlay the population onto Rogers' adopter segments — **innovators 2.5%, early adopters 13.5%, early majority 34%, late majority 34%, laggards 16%** ([Rogers, 2003](#ev-rogers-diffusion-2003-adopter-categories)) — and locate where adoption has stalled.

The decisive boundary is between the early adopters and the early majority. The enthusiasts (the first ~16%) adopt on novelty; the majority adopt only on proof, and the transition between them is where most programs stall — the "chasm" ([Moore, 1991](#ev-moore-crossing-the-chasm-1991-chasm)). Practical use of the map:

- **Stuck before ~16% penetration** ([Rogers, 2003](#ev-rogers-diffusion-2003-adopter-categories)) → you have reached the enthusiasts and no further. The constraint is usually proof and relevance, not access — invest in role-based use cases and visible peer wins (D4).
- **Stuck at the majority** → the constraint is usually safety and manager engagement (D2, D3) — pragmatists adopt when their manager and peers visibly do.
- **High usage but concentrated** → breadth problem; check D1 breadth and the champion coverage feeding it.

Segment the resistance, too: fear of job loss, fear of looking incompetent, distrust of outputs, and loss of autonomy call for different responses (see the [framework](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md)). Mapping *which* fear dominates *which* segment tells the program where to aim.

---

## Scoring and Interpretation

Record a 1–5 for each dimension and read the **profile**, not just the mean. The shape is diagnostic:

| Pattern | What it means | Where to act |
|---|---|---|
| High D1, low D2/D5 | Usage is real but unsafe and ungoverned — the shadow-AI pattern: people are using AI, often unsanctioned, and hiding it | Build safety and channel demand into sanctioned tools ([program guide](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/03-practitioner-guide-designing-an-adoption-program.md), Phases 4–5) |
| High D3/D4, low D1 | Investment is not converting — the access-vs-use gap: leadership and training are in place but habitual use is missing | Check relevance and friction; role-based use cases, remove workflow blockers |
| High everything except D6 | Adoption is broad but trust is uncalibrated — over- or under-trust risk | Teach verification habits matched to task risk (D6) |
| Uniformly low | Early stage | Start at Phase 0 — sponsorship and governance — before anything else |

Two interpretation rules hold across patterns. First, **a high mean does not redeem a low bottleneck dimension** — adoption is gated by its weakest link, much as the [framework](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) argues culture gates the whole transformation. Second, **trend beats level**: re-score on a regular cadence, because a rising score that plateaus at the majority is the signal to change tactics, not to keep doing more of what reached the enthusiasts.

---

## Key Takeaways

- **Score use, not access.** Trial and licenses overstate adoption; habitual, deep, workflow-integrated use is the real measure ([Slack, 2024](#ev-slack-workforce-index-2024-tried-ai); [Slack, 2025](#ev-slack-new-ai-advantage-2025-usage-frequency)).
- **Six dimensions, scored as a profile.** Utilization, culture, leadership, enablement, governance, and verification — read the shape, because the weakest dimension is the bottleneck.
- **Engagement is measurable.** Activation, DAU/MAU (~31% B2B-SaaS benchmark), retention, breadth, and license waste give D1 an evidence base ([Mixpanel, 2026](#ev-mixpanel-mau-benchmarks-2026-b2b-stickiness); [Zylo, 2024](#ev-zylo-saas-management-index-2024-license-utilization)).
- **Map the resistance.** Use Rogers' segments to find where adoption stalls — most often at the chasm between enthusiasts and the pragmatic majority ([Rogers, 2003](#ev-rogers-diffusion-2003-adopter-categories); [Moore, 1991](#ev-moore-crossing-the-chasm-1991-chasm)).
- **Re-score on a cadence.** Maturity is a trend, not a one-time grade; the profile tells you which [program](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/03-practitioner-guide-designing-an-adoption-program.md) phase to invest in next.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Slack Workforce Lab — *Workforce Index (June 2024)*, 2024.** 32% of desk workers have experimented with AI tools; only 15% of global desk workers strongly agree that they have the education and training necessary to use AI effectively. [View source](https://slack.com/blog/news/the-workforce-index-june-2024){#ev-slack-workforce-index-2024-tried-ai} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *The New AI Advantage*, 2025.** Three in five desk workers use AI at least occasionally, two in five use it weekly, and one in five use it daily. [View source](https://slack.com/blog/news/the-new-ai-advantage){#ev-slack-new-ai-advantage-2025-usage-frequency} · verified 2026-06-20 · primary
- **CMMI Institute (ISACA) — *Capability Maturity Model Integration*, 2018.** CMMI defines five maturity levels: Initial, Managed, Defined, Quantitatively Managed, and Optimizing. [View source](https://cmmiinstitute.com/learning/appraisals/levels){#ev-cmmi-maturity-levels-five-stage} · verified 2026-06-20 · primary
- **Amplitude — *Top Digital Product Adoption Metrics*, 2025.** The activation rate gauges the percentage of users who complete a predefined action that signifies meaningful engagement with the product. [View source](https://amplitude.com/blog/top-digital-product-adoption-metrics){#ev-amplitude-product-adoption-metrics-activation} · verified 2026-06-20 · primary
- **Mixpanel — *MAU: Definition, Formula, and Benchmarks*, 2026.** B2B SaaS stickiness averages about 31% across North America and EMEA; a product sitting between 25% and 35% is broadly in line with the market. [View source](https://mixpanel.com/blog/mau/){#ev-mixpanel-mau-benchmarks-2026-b2b-stickiness} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *The New AI Advantage*, 2025.** The share of workers using AI every day has more than doubled in six months and is now 233% higher than it was in November 2024. [View source](https://slack.com/blog/news/the-new-ai-advantage){#ev-slack-new-ai-advantage-2025-daily-use-growth} · verified 2026-06-20 · primary
- **Zylo — *SaaS Management Index*, 2024.** Companies are only using half (49%) of their provisioned SaaS licenses. [View source](https://zylo.com/news/2024-saas-management-index/){#ev-zylo-saas-management-index-2024-license-utilization} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *The New AI Advantage*, 2025.** Casual users (less than once a week) show little to no difference in outcomes from non-users; weekly users see gains, but the biggest impact comes from integrating AI into the daily workflow. [View source](https://slack.com/blog/news/the-new-ai-advantage){#ev-slack-new-ai-advantage-2025-daily-user-outcomes} · verified 2026-06-20 · primary
- **Amy C. Edmondson — *Psychological Safety and Learning Behavior in Work Teams (Administrative Science Quarterly, 44(2), 350-383)*, 1999.** A shared belief held by members of a team that the team is safe for interpersonal risk taking; team psychological safety is associated with learning behavior, which mediates between psychological safety and team performance. [View source](https://doi.org/10.2307/2666999){#ev-edmondson-1999-psychological-safety} · verified 2026-06-20 · primary
- **Google re:Work — *Project Aristotle: Understand Team Effectiveness*, 2015.** Psychological safety was far and away the most important of the five dynamics we found; it is the underpinning of the other four. [View source](https://rework.withgoogle.com/guides/understanding-team-effectiveness/){#ev-google-project-aristotle-2015-psych-safety} · verified 2026-06-20 · primary
- **Slack Workforce Lab — *Fall 2024 Workforce Index*, 2024.** Those who are comfortable sharing that they used AI for work tasks are 67% more likely to have used AI for work than those who would not be comfortable admitting AI use. [View source](https://slack.com/blog/news/the-fall-2024-workforce-index-shows-executives-and-employees-investing-in-ai-but-uncertainty-holding-back-adoption){#ev-slack-workforce-index-2024-disclosure-comfort} · verified 2026-06-20 · primary
- **KPMG & University of Melbourne — *Trust, Attitudes and Use of AI: A Global Study 2025*, 2025.** Only 46% of people globally are willing to trust AI systems. [View source](https://kpmg.com/xx/en/our-insights/ai-and-technology/trust-attitudes-and-use-of-ai.html){#ev-kpmg-trust-ai-2025-willing-to-trust} · verified 2026-06-20 · primary
- **Everett M. Rogers — *Diffusion of Innovations (5th ed.; ISBN 978-0743222099)*, 2003.** Adopter categories: innovators 2.5%, early adopters 13.5%, early majority 34%, late majority 34%, laggards 16%, obtained by partitioning the normal adoption distribution at the mean plus or minus one and two standard deviations. [View source](https://www.simonandschuster.com/books/Diffusion-of-Innovations-5th-Edition/Everett-M-Rogers/9780743222099){#ev-rogers-diffusion-2003-adopter-categories} · verified 2026-06-20 · ⚠ secondary mirror
- **Geoffrey A. Moore — *Crossing the Chasm*, 1991.** Moore identifies a chasm between the early adopters (visionaries) and the early majority (pragmatists): the gap where most high-tech adoption efforts stall. [View source](https://www.harpercollins.com/products/crossing-the-chasm-3rd-edition-geoffrey-a-moore){#ev-moore-crossing-the-chasm-1991-chasm} · verified 2026-06-20 · primary
