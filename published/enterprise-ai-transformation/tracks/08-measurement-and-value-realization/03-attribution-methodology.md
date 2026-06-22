---
type: Playbook
title: "Attribution Methodology"
description: "How to isolate AI's impact from confounding variables, choose direct vs. indirect attribution models, and build a defensible investment case from measurement data."
tags: [measurement, attribution, roi, playbook]
timestamp: "2026-06-18"
---

> If you cannot say what *would have happened without the AI*, you have not measured its value — you have measured a coincidence.

Most organizations are stuck at the coincidence stage. Only 39% attribute *any* level of EBIT impact to AI, and most of those report under 5% of EBIT; roughly six in ten cannot tie any EBIT to AI at all, with only about 6% qualifying as high performers who attribute more than 5% of EBIT to it ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-ebit-any); [McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-high-performers)). The picture from other surveys is just as stark: 74% of companies have yet to show tangible value from AI, and only 26% have moved past proof-of-concept to generate value — of which a mere 4% have built cutting-edge cross-functional capability ([BCG, 2024](#ev-bcg-value-2024-beyond-poc)). Gartner projected that at least 30% of gen-AI projects would be abandoned after proof of concept by the end of 2025, citing unclear business value among the causes ([Gartner, 2024](#ev-gartner-genai-poc-2024-abandonment)). And in one of the bluntest findings, 95% of enterprise gen-AI pilots delivered no measurable P&L impact ([MIT Project NANDA, 2025](#ev-mit-nanda-genai-divide-2025-no-pl-impact)).

This page is the bridge from "we deployed AI" to "AI created $X, and here is how we know." It covers the attribution problem, the methods that actually isolate impact, the difference between direct and indirect value, how to convert measurement into a defensible investment case, and the errors that quietly invalidate the whole exercise.

## The Attribution Problem

Attribution is hard for four structural reasons, and each one defeats a naive "we turned it on and revenue went up" story.

- **Confounding variables.** Revenue, cycle time, and quality move for dozens of reasons at once — a pricing change, a new hire cohort, a seasonal swing, a competitor stumble. Any of these can masquerade as AI impact, or mask it.
- **The counterfactual is unobservable.** You only ever see the world where the team had AI. You never directly see the same team, same quarter, *without* it. Every credible attribution method is, at heart, a way to estimate that missing counterfactual.
- **Hard-to-monetize outcomes.** Much of AI's early value shows up as quality, speed, employee experience, or capability — things that are real but resist a clean dollar figure. Deloitte found that 41% of organizations have struggled to define and measure the exact impacts of their gen-AI efforts ([Deloitte, 2024](#ev-deloitte-state-genai-2024-measure-impacts-struggle)).
- **Long and lumpy payback.** Productivity gains often precede financial results by quarters. Cutting the analysis off too early shows "no impact" when the value simply has not landed in the P&L yet.

The combined effect is the credibility gap above: the technology can be working at the desk while the boardroom sees nothing it trusts.

## Methods for Isolating Impact

There is a hierarchy of attribution methods, ranked by how well each one reconstructs the counterfactual. Use the strongest method your context allows, and be explicit about which one you used — it determines how much confidence the number deserves.

| Rank | Method | Counterfactual logic | Use when | Strength |
|------|--------|----------------------|----------|----------|
| 1 | **RCT / A-B test** | Randomly assign AI access; the control group *is* the counterfactual | You can randomize at the user or task level | Strongest — isolates causation |
| 2 | **Holdout / control group** | A comparable non-randomized group that does not get AI | Randomization is impractical but a similar cohort exists | Strong, if groups are truly comparable |
| 3 | **Difference-in-differences (DiD)** | Compare the *change* in treated vs. untreated groups over time | You have before/after data for both a treated and an untreated group | Strong, if the parallel-trends assumption holds |
| 4 | **Before/after (pre-post)** | The same group before vs. after | Nothing else is available | Weakest — no control for confounders |

**Why randomization wins.** In a randomized controlled trial, the only systematic difference between groups is the AI itself, so any outcome gap is causal. The landmark GitHub Copilot RCT did exactly this: developers using Copilot completed the task 55.8% faster — 1 hour 11 minutes versus 2 hours 41 minutes — in a randomized trial of 95 developers ([Peng et al., 2023](#ev-peng-copilot-rct-2023-speedup)). A pre-post comparison could never have ruled out "the developers just got better at the task"; randomization does.

**Difference-in-differences and the parallel-trends assumption.** When you cannot randomize, DiD compares the *change* in the treated group to the *change* in an untreated group over the same window. It subtracts out anything that affected both groups equally — seasonality, macro shifts. The critical condition is **parallel trends**: the two groups must have been moving in step *before* the intervention, so that the untreated group's post-period change is a fair estimate of what the treated group would have done absent the AI. The canonical example is the study of a customer-support gen-AI assistant, which raised productivity (issues resolved per hour) by 15% on average and 30% for the least-experienced workers, identified via difference-in-differences on a staggered rollout across roughly 5,172 agents ([Brynjolfsson et al., 2025](#ev-brynjolfsson-generative-ai-at-work-2025-did-productivity)). The staggered rollout is what made it work — agents who had not yet received the tool served as the control for those who had.

**Attribution must respect *where* AI helps.** A pre-registered RCT of 758 BCG consultants found that those using GPT-4 completed 12.2% more tasks, 25.1% faster, with 40% higher quality — but only on tasks inside the AI's "jagged frontier." On tasks outside that frontier, AI users were 19 percentage points *less* likely to be correct ([Dell'Acqua et al., 2023](#ev-dellacqua-jagged-frontier-2023-bcg-rct)). The lesson for attribution: an aggregate average can hide both a strong positive and a real negative. Segment your measurement by task type, or you will attribute a blended number that is true on average and wrong everywhere.

## Direct vs. Indirect Attribution

Measured value splits into two families, and mature programs report both — while being honest about which is which.

**Direct attribution** captures *lagging financial* outcomes that flow to the P&L:

- Time saved (hours returned to higher-value work)
- Cost reduced (lower cost-to-serve, fewer vendor hours, deflected tickets)
- Revenue gained (faster sales cycles, higher conversion, new AI-enabled offerings)

These are what the CFO wants, because they are denominated in dollars and tie to the income statement.

**Indirect attribution** captures *leading* indicators that predict future financial value but do not yet appear as cash:

- Quality (defect rates, rework, accuracy)
- Satisfaction (customer CSAT/NPS, employee experience)
- Capability (skills built, faster onboarding, broader adoption)
- Option value (new capabilities that open future opportunities)

**The CFO-comfort problem.** Indirect value is real but uncomfortable for finance, because it is not yet money. This is why so few programs close the loop with the office of the CFO: only 16% of organizations produce regular reports to the CFO on the value created by gen AI ([Deloitte, 2024](#ev-deloitte-state-genai-2024-cfo-reports)). The fix is not to abandon indirect metrics — they are your early-warning system — but to (a) report them as leading indicators with an explicit hypothesis of how they convert to financial outcomes, and (b) never *count* them as dollars until they show up as direct value.

## Building the Investment Case

The job here is to convert measured productivity into financial terms a CFO will sign, then deliberately discount it.

**The productivity-to-dollars formula** (standard practice):

```
Annual $ value =
    hours saved per user
  × fully-loaded hourly labor cost
  × number of active users
  × adoption / utilization rate
  × realization rate (haircut)
```

Two terms carry most of the rigor:

- **Fully-loaded hourly labor cost** is *not* base salary. It is salary + benefits + payroll taxes + overhead (facilities, equipment, management), converted to an hourly rate. Using base salary alone understates the value; using a market bill rate often overstates it. Pick one definition and document it.
- **Active users, not licenses.** A purchased license is not a user, and a user is not a *daily* user. The single most common way these models inflate is by multiplying by seats sold rather than people actively getting value. Drive the model off observed adoption and utilization, not procurement.

**The realization rate (haircut)** is the deliberate discount that turns a theoretical maximum into a defensible claim. Not every saved hour is reinvested in productive work; some leaks to slack. Conservative haircutting is what makes finance trust the number. Forrester's Total Economic Impact (TEI) methodology formalizes this with four components — **Benefits, Costs, Flexibility, and Risk** — and systematically adjusts benefits *down* and costs *up* (in one study, benefits were cut 10% and costs raised 10%), then applies a discount rate typically in the 8–16% range to account for the time value of money ([Forrester, TEI methodology](#ev-forrester-tei-methodology-framework)). Adopt the same posture: present a conservative case, not a ceiling.

For external benchmarking, organizations realized an average return of $3.70 for every $1 invested in generative AI ([IDC, 2024](#ev-idc-business-value-genai-2024-roi-per-dollar)) — useful as a sanity check on your own modeled return, not as a substitute for measuring it.

A worked sketch: 100 hours saved per user per year × $75 fully-loaded hourly cost × 400 active users × 70% utilization × 60% realization = $1.26M per year. Drop the 60% haircut, and the same model reads $2.1M; swap "active users" for "licenses sold" and it inflates further still — which is exactly how investment cases lose credibility.  <!-- noev: worked-example arithmetic, not a sourced statistic -->

## Common Attribution Errors

- **Correlation ≠ causation.** "Revenue rose after we deployed AI" is not attribution; it is a timeline. Without a counterfactual, it proves nothing.
- **No baseline.** If you did not capture the pre-AI metric, you cannot compute a delta. Baseline before you deploy, not after.
- **No control.** A pre-post number with no comparison group cannot separate AI from everything else that changed that quarter.
- **Ignoring value leakage.** Time saved that is not redeployed to valuable work — a saved hour that gets absorbed by meetings — is not realized value. Haircut for it.
- **Conflating share-of-code (or share-of-output) with acceptance, or acceptance with value.** "X% of code is AI-generated" is an activity metric, not an outcome. Accepted suggestions are not the same as faster delivery, which is not the same as business value.
- **Double-counting.** Counting the same hour saved in two teams' cases, or counting indirect value as both a leading indicator *and* as direct dollars, inflates the total. Each unit of value belongs to exactly one line.

## Key Takeaways

- **Attribution is counterfactual estimation.** Every defensible number answers "what would have happened without the AI?" — pick the strongest method (RCT > holdout > DiD > pre-post) your context allows.
- **The landmark studies prove the methods work** — Copilot's 55.8% RCT speedup ([Peng et al., 2023](#ev-peng-copilot-rct-2023-speedup)) and the 15%/30% DiD support-productivity result ([Brynjolfsson et al., 2025](#ev-brynjolfsson-generative-ai-at-work-2025-did-productivity)) are templates, not just headlines.
- **Segment by where AI helps.** A blended average can hide a real negative outside the "jagged frontier" ([Dell'Acqua et al., 2023](#ev-dellacqua-jagged-frontier-2023-bcg-rct)).
- **Report direct and indirect value separately**, and never count leading indicators as dollars — that is what builds CFO trust, which today is rare ([Deloitte, 2024](#ev-deloitte-state-genai-2024-cfo-reports)).
- **Build the case conservatively.** Drive the model off active users, use fully-loaded labor cost, apply a realization-rate haircut, and adjust benefits down / costs up in the spirit of TEI ([Forrester, TEI methodology](#ev-forrester-tei-methodology-framework)).
- **Avoid the silent invalidators** — no baseline, no control, value leakage, share-of-output vanity metrics, and double-counting.

---

**Companion pages:** start with the [measurement framework](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md) for the metric model this attribution sits on top of, then use the [standing up AI measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/04-practitioner-guide-standing-up-ai-measurement.md) practitioner guide to instrument the data, and the [measurement maturity scoring](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/05-assessment-measurement-maturity-scoring.md) assessment to gauge readiness. For where the productivity actually originates, see the [workflow optimization framework](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md); for how attributed value feeds prioritization, see the [AI strategy framework](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/02-ai-strategy-framework.md).

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **McKinsey — *The State of AI*, 2025.** About 39% of organizations report any enterprise-level EBIT impact from AI; most of those say less than 5% of EBIT is attributable to AI use. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-ebit-any} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI*, 2025.** Respondents who attribute EBIT impact of 5 percent or more to AI use and say their organization has seen significant value from AI — about 6 percent of respondents — are defined as AI high performers. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-high-performers} · verified 2026-06-20 · primary
- **BCG — *Where's the Value in AI?*, 2024.** Only 26% of companies have developed the necessary set of capabilities to move beyond proofs of concept and generate tangible value (4% cutting-edge plus 22% advanced). [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-value-2024-beyond-poc} · verified 2026-06-20 · primary
- **Gartner — *Gartner Predicts 30% of Generative AI Projects Will Be Abandoned After Proof of Concept By End of 2025*, 2024.** At least 30% of generative AI projects will be abandoned after proof of concept by the end of 2025, due to poor data quality, inadequate risk controls, escalating costs or unclear business value. [View source](https://www.gartner.com/en/newsroom/press-releases/2024-07-29-gartner-predicts-30-percent-of-generative-ai-projects-will-be-abandoned-after-proof-of-concept-by-end-of-2025){#ev-gartner-genai-poc-2024-abandonment} · verified 2026-06-20 · primary
- **MIT Project NANDA — *The GenAI Divide: State of AI in Business 2025*, 2025.** Just 5% of integrated AI pilots are extracting millions in value, while the vast majority remain stuck with no measurable P&L impact. [View source](https://mlq.ai/media/quarterly_decks/v0.1_State_of_AI_in_Business_2025_Report.pdf){#ev-mit-nanda-genai-divide-2025-no-pl-impact} · verified 2026-06-20 · ⚠ secondary mirror
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** 41% have struggled to define and measure the exact impacts of their GenAI efforts. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-measure-impacts-struggle} · verified 2026-06-20 · primary
- **Peng et al. — *The Impact of AI on Developer Productivity: Evidence from GitHub Copilot*, 2023.** The treatment group with access to the AI pair programmer completed the task 55.8% faster than the control group; developers with GitHub Copilot took on average 1 hour 11 minutes versus 2 hours 41 minutes, across 95 professional programmers. [View source](https://arxiv.org/abs/2302.06590){#ev-peng-copilot-rct-2023-speedup} · verified 2026-06-20 · primary
- **Brynjolfsson, Li & Raymond — *Generative AI at Work (Quarterly Journal of Economics)*, 2025.** Access to AI assistance increases issues resolved per hour by 15% on average, with a 30% increase for less-skilled and less-experienced workers, using data from 5,172 customer-support agents. [View source](https://academic.oup.com/qje/article/140/2/889/7990658){#ev-brynjolfsson-generative-ai-at-work-2025-did-productivity} · verified 2026-06-20 · primary
- **Dell'Acqua et al. — *Navigating the Jagged Technological Frontier (HBS Working Paper 24-013)*, 2023.** In a pre-registered experiment with 758 consultants, those using AI inside the frontier completed 12.2% more tasks, 25.1% more quickly, with more than 40% higher quality; on a task outside the frontier AI users were 19 percentage points less likely to be correct. [View source](https://www.hbs.edu/faculty/Pages/item.aspx?num=64700){#ev-dellacqua-jagged-frontier-2023-bcg-rct} · verified 2026-06-20 · primary
- **Deloitte — *The State of Generative AI in the Enterprise: Now decides Next (Q3)*, 2024.** Only 16% have produced regular reports for the CFO about the value being created with GenAI. [View source](https://www.deloitte.com/us/en/about/press-room/state-of-generative-ai-Q3.html){#ev-deloitte-state-genai-2024-cfo-reports} · verified 2026-06-20 · primary
- **Forrester — *Total Economic Impact (TEI) Methodology*.** Forrester's Total Economic Impact methodology evaluates investment value across four components (Benefits, Costs, Flexibility, Risk), risk-adjusts the model (reducing benefits and increasing costs for uncertainty), and discounts future cash flows. [View source](https://www.forrester.com/policies/tei/){#ev-forrester-tei-methodology-framework} · verified 2026-06-20 · primary
- **IDC — *The Business Opportunity of AI (IDC InfoBrief, sponsored by Microsoft)*, 2024.** For every $1 a company invests in generative AI, the average ROI is 3.7x. [View source](https://blogs.microsoft.com/blog/2024/11/12/idcs-2024-ai-opportunity-study-top-five-ai-trends-to-watch/){#ev-idc-business-value-genai-2024-roi-per-dollar} · verified 2026-06-20 · ⚠ secondary mirror
