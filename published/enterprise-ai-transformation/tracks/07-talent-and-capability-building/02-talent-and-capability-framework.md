---
type: Concept
title: "Talent & Capability Framework"
description: "The capability stack an AI-mature organization needs, the four levels of AI literacy, and how to decide between building, hiring, and partnering for capability."
tags: [talent, capability-building, ai-literacy]
timestamp: "2026-06-18"
---

## Why This Matters Now

When organizations are asked what is actually holding back their AI transformation, the answer is rarely the technology. It is people. McKinsey's global survey found that **47% of C-suite leaders say their organizations are developing and deploying gen-AI tools too slowly — and among those leaders, the single most-cited reason is talent and skill gaps (46%, ahead of resourcing constraints at 38%)** ([McKinsey, 2025](#ev-mckinsey-superagency-2025-too-slow-skill-gaps)). The World Economic Forum reaches the same conclusion from the demand side: **63% of employers name the skills gap as the single biggest barrier to business transformation through 2030** ([WEF, 2025](#ev-wef-future-of-jobs-2025-skills-gap-barrier)).

The gap is widening because the work itself is changing underneath people. The WEF estimates that **39% of the core skills workers need will change by 2030** (down from 44% in 2023, but still more than a third of the skill base in motion), and that on current trends **170 million new roles will be created and 92 million displaced — a net gain of 78 million, with churn touching 22% of all jobs** ([WEF, 2025](#ev-wef-future-of-jobs-2025-skill-disruption); [WEF, 2025](#ev-wef-future-of-jobs-2025-jobs-churn)). Meanwhile the market is already pricing the scarcity: PwC found that **jobs demanding AI skills now carry a 56% wage premium, up from 25% a year earlier** ([PwC, 2025](#ev-pwc-ai-jobs-barometer-2025-wage-premium)).

> Talent is the binding constraint. The tools are bought and switched on; the gap is between the capability an organization *has licensed* and the capability its *people can actually exercise*.

This page defines that human capability layer: the **capability stack** an AI-mature organization needs, the **four levels of AI literacy** that let you talk about skill precisely, the **build-vs-hire-vs-partner** decision for closing gaps, the role of **internal champions**, and why talent readiness gates every other track in this framework. Its companion pages give you the method to [redesign roles task-by-task](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/03-role-redesign-methodology.md), a [roadmap for building capability](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/04-practitioner-guide-capability-building-roadmap.md), and a way to [score where you stand](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/05-assessment-talent-readiness-scoring.md).

---

## The Capability Stack

Capability is not one thing. An organization that can put AI to work at scale has assembled a *stack* — several distinct layers, each of which can be the bottleneck:

- **Foundational AI literacy (everyone).** A shared, baseline understanding of what generative AI is, where it is strong and where it fails, and how to use it responsibly. This is no longer optional: under the **EU AI Act's Article 4 AI-literacy obligation, in force since 2 February 2025**, providers and deployers must ensure a sufficient level of AI literacy among staff who operate AI systems on their behalf ([European Commission, 2024](#ev-european-commission-eu-ai-act-2024-article-4-literacy)).
- **Applied fluency (most knowledge workers).** The ability to use AI fluently inside one's own domain — to direct it, evaluate its output, and integrate it into daily work. This is where most of the productivity is won or lost.
- **Builder capability (a meaningful minority).** People who can compose, configure, and orchestrate AI — building agents, automations, retrieval pipelines, and custom workflows on top of vendor platforms.
- **Architect and specialist capability (a small core).** Deep technical talent — ML engineers, data scientists, MLOps, AI-platform owners — who stand up and run the infrastructure the rest of the organization builds on. This layer connects directly to the [technology architecture track](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md).
- **Leadership and governance capability (executives and managers).** The ability to make sound build/buy bets, set risk appetite, and lead teams through changed work — the literacy that lets [strategy](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/02-ai-strategy-framework.md) and [governance](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md) actually function.

The common mistake is to invest only at the top of the stack — to hire a few specialists and declare the talent problem solved — while the broad middle layers, where most of the value compounds, stay at zero. A handful of architects cannot move an organization that has no applied fluency beneath them.

---

## The Four Levels of AI Literacy

To plan capability you need a vocabulary precise enough to set targets against. We use four levels, ascending. Most organizations should aim to move the bulk of their workforce to **Level 2**, while deliberately growing a smaller population at Levels 3 and 4.

1. **Awareness.** Knows what generative AI is and is not, understands the headline risks (hallucination, data leakage, bias), and can use a chat assistant for simple, well-bounded tasks. The floor the EU AI Act effectively mandates.
2. **Fluency.** Uses AI confidently for real work in their own domain — directs it with good prompts, recognizes and corrects weak output, and knows which tasks to hand it and which to keep. This is *calibrated trust* applied as a daily skill, and it is the level that produces the [adoption](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) most organizations are missing.
3. **Builder.** Goes beyond using a tool to composing one — chains prompts, configures agents and automations, wires up retrieval over internal data, and ships repeatable AI-enabled workflows for a team. Builders are the multiplier between the specialist core and the fluent majority.
4. **Architect.** Designs and operates the underlying systems — models, pipelines, evaluation harnesses, and platform guardrails — and makes the technical trade-offs that everyone else inherits.

Treating "AI skills" as a single binary (trained / not trained) is what produces incoherent programs. A literacy *ladder* lets you set differentiated targets by role and measure progress against them — the basis of the [talent-readiness assessment](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/05-assessment-talent-readiness-scoring.md).

---

## Build vs. Hire vs. Partner

Every capability gap can be closed three ways, and mature organizations use all three deliberately rather than defaulting to one.

- **Build (reskill from within).** Develop existing employees up the literacy ladder. This is usually the cheapest and most durable option for the broad fluency layers, and it preserves institutional knowledge — the person already understands the business; you are adding the AI skill, not the context. The WEF's reskilling analysis finds a **clear financial case for redeploying at-risk workers rather than replacing them**, and **85% of employers plan to prioritize upskilling their workforce** through 2030 ([WEF, 2025](#ev-wef-future-of-jobs-2025-upskilling-priority)).
- **Hire (buy the capability).** Bring in specialist talent for the architect/specialist core where internal development is too slow. This is the most expensive and most competitive option — the 56% AI-skills wage premium is the price tag ([PwC, 2025](#ev-pwc-ai-jobs-barometer-2025-wage-premium)) — and it works best for a small, deep core rather than for broad capability.
- **Partner (rent the capability).** Use external providers, system integrators, and managed services to access capability you do not need to own permanently, or to bridge while you build. Best for spikes, specialized one-off needs, and accelerating the early stages.

The decision rule: **build the broad middle, hire the deep core, partner for the spikes and the bridge.** The most common failure is to over-hire for capability that should have been built (expensive, and the knowledge walks out the door) or to over-partner for capability that should have been owned (you never develop the muscle internally). This same logic recurs concretely in the [capability-building roadmap](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/04-practitioner-guide-capability-building-roadmap.md).

---

## The Role of Internal Champions

Capability does not diffuse evenly on its own. The mechanism that carries fluency across an organization is a network of **internal champions** — practitioners, embedded in their own teams, who are a level ahead and who model, coach, and translate AI use into the specific language of their function.

Champions matter because the alternative — centralized training pushed from the top — consistently underperforms peer-led diffusion. The Microsoft and LinkedIn Work Trend Index found that **75% of knowledge workers already use AI at work, yet only 39% of those who use it have received any training from their employer** ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-use-at-work); [Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-training-hiring)). People are learning AI from each other, not from the L&D catalog. A champions network makes that organic diffusion deliberate: it gives the self-taught majority someone credible and nearby to learn from, surfaces the use cases that actually work in each function, and feeds them back to the center. This is the human distribution layer that the [adoption program](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/03-practitioner-guide-designing-an-adoption-program.md) operationalizes.

---

## Why Talent Readiness Gates Every Other Track

Talent is the layer the rest of the framework rests on. A sophisticated [platform](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md) is inert if no one can build on it. [Workflow redesign](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md) cannot happen if the people doing the work lack the fluency to see where AI fits. [Governance](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md) fails when staff cannot recognize the risks they are told to manage. And [value never shows up in measurement](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md) because the capability to convert tools into changed work was never built.

This is why so much AI investment strands: the spend goes to licenses and infrastructure, while the capability layer that would have turned them into outcomes is left at zero. The evidence that the human-and-process layer dominates is consistent — BCG estimates the effort split for value capture at roughly **10% algorithms, 20% technology and data, and 70% people and process** ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy)). Talent and capability building is the discipline of that 70%, applied to the workforce.

---

## Key Takeaways

- **Talent is the binding constraint, not technology.** Among the 47% of leaders who say gen-AI deployment is too slow, skill gaps are the most-cited reason (46%) ([McKinsey, 2025](#ev-mckinsey-superagency-2025-too-slow-skill-gaps)).
- **Capability is a stack, not a number.** Literacy for everyone, fluency for most, builders for the multiplier layer, and a small architect/specialist core — under-investing in the broad middle is the common error.
- **Use four literacy levels — awareness, fluency, builder, architect — to set differentiated targets** rather than treating "AI skills" as a binary. Aim the bulk of the workforce at fluency.
- **Build the broad middle, hire the deep core, partner for spikes and bridges.** Reskilling is usually cheaper and more durable than hiring against a 56% AI-skills wage premium ([PwC, 2025](#ev-pwc-ai-jobs-barometer-2025-wage-premium); [WEF, 2025](#ev-wef-future-of-jobs-2025-upskilling-priority)).
- **Champions are the distribution layer.** Most people already learn AI from peers, not L&D — 75% use it, only 39% were trained ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-use-at-work); [Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-training-hiring)) — so make peer diffusion deliberate.
- **Talent readiness gates every other track.** The 70% of value-capture effort that is people-and-process is what this track is about ([BCG, 2024](#ev-bcg-2024-ten-twenty-seventy)).

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **McKinsey — *Superagency in the Workplace*, 2025.** 47% of US C-suite executives said their organizations are moving too slow on AI; among them the biggest reason was talent skill gaps (46%), ahead of resourcing constraints (38%). [View source](https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/superagency-in-the-workplace-empowering-people-to-unlock-ais-full-potential-at-work){#ev-mckinsey-superagency-2025-too-slow-skill-gaps} · verified 2026-06-20 · ⚠ secondary mirror
- **World Economic Forum — *Future of Jobs Report 2025*, 2025.** The skills gap continues to be the most significant barrier to business transformation today, with 63% of employers already citing it as the key barrier they face. [View source](https://www.weforum.org/publications/the-future-of-jobs-report-2025/){#ev-wef-future-of-jobs-2025-skills-gap-barrier} · verified 2026-06-20 · primary
- **World Economic Forum — *Future of Jobs Report 2025*, 2025.** On average, workers can expect that two-fifths (39%) of their existing skill sets will be transformed or become outdated over the 2025-2030 period; down from 44% in the 2023 edition. [View source](https://www.weforum.org/publications/the-future-of-jobs-report-2025/){#ev-wef-future-of-jobs-2025-skill-disruption} · verified 2026-06-20 · primary
- **World Economic Forum — *Future of Jobs Report 2025*, 2025.** Current trends are expected to create 170 million new jobs by 2030 while displacing 92 million existing jobs, resulting in net growth of 78 million jobs; this structural churn amounts to 22% of today's total jobs. [View source](https://www.weforum.org/publications/the-future-of-jobs-report-2025/){#ev-wef-future-of-jobs-2025-jobs-churn} · verified 2026-06-20 · primary
- **PwC — *Global AI Jobs Barometer*, 2025.** Jobs requiring AI skills offer a wage premium in every industry analysed, with the average premium hitting 56%, up from 25% the previous year. [View source](https://www.pwc.com/gx/en/issues/artificial-intelligence/ai-jobs-barometer.html){#ev-pwc-ai-jobs-barometer-2025-wage-premium} · verified 2026-06-20 · primary
- **European Commission — *EU AI Act (Regulation (EU) 2024/1689), Article 4 - AI literacy*, 2024.** Providers and deployers of AI systems shall take measures to ensure, to their best extent, a sufficient level of AI literacy of their staff and other persons dealing with the operation and use of AI systems on their behalf; per Article 113, Chapters I and II (which include Article 4) shall apply from 2 February 2025. [View source](https://eur-lex.europa.eu/eli/reg/2024/1689/oj){#ev-european-commission-eu-ai-act-2024-article-4-literacy} · verified 2026-06-20 · primary
- **World Economic Forum — *Future of Jobs Report 2025*, 2025.** Upskilling is the most common workforce strategy for 2025-2030, with 85% of surveyed employers anticipating it; of a representative 100 workers, employers foresee 29 upskilled in their current roles and 19 upskilled and redeployed elsewhere, while 11 are unlikely to receive the reskilling needed. [View source](https://www.weforum.org/publications/the-future-of-jobs-report-2025/){#ev-wef-future-of-jobs-2025-upskilling-priority} · verified 2026-06-20 · primary
- **Microsoft & LinkedIn — *2024 Work Trend Index Annual Report*, 2024.** 75% of knowledge workers now use AI at work. [View source](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part){#ev-microsoft-work-trend-2024-use-at-work} · verified 2026-06-20 · primary
- **Microsoft & LinkedIn — *2024 Work Trend Index Annual Report*, 2024.** Only 39% of people who use AI at work have received AI training from their company; 66% of leaders say they would not hire someone without AI skills. [View source](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part){#ev-microsoft-work-trend-2024-training-hiring} · verified 2026-06-20 · primary
- **BCG — *Where's the Value in AI?*, 2024.** AI leaders follow the rule of putting 10% of their resources into algorithms, 20% into technology and data, and 70% into people and processes. [View source](https://www.bcg.com/publications/2024/wheres-value-in-ai){#ev-bcg-2024-ten-twenty-seventy} · verified 2026-06-20 · primary
