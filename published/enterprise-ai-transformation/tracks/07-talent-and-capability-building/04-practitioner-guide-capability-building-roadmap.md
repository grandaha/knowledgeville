---
type: Playbook
title: "Practitioner Guide: Capability Building Roadmap"
description: "How to build a capability development roadmap — AI literacy programs, fluency tiers, internal champions, and external partners."
tags: [talent, capability-building, practitioner-guide, playbook]
timestamp: "2026-06-18"
---

## What This Guide Builds

A capability-building roadmap is the operational plan that closes the gap between the talent an organization *has* and the talent its AI ambitions *require*. It turns the [Talent & Capability Framework](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/02-talent-and-capability-framework.md) into a sequenced program: who needs to reach which [literacy level](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/02-talent-and-capability-framework.md), by when, through what mechanism, and how you will know it worked.

The urgency is documented and the default is failure-by-neglect. The Microsoft and LinkedIn Work Trend Index found that **75% of knowledge workers already use AI at work, yet only 39% of those users have received any AI training from their employer, and just 25% of companies planned to offer generative-AI training that year** *(Microsoft & LinkedIn, Work Trend Index, 2024)*. The same study found **78% of AI users are bringing their own tools to work** ("BYOAI") — using AI with no guidance, no guardrails, and no shared standard *(Microsoft & LinkedIn, Work Trend Index, 2024)*. A roadmap is how you replace ungoverned, self-taught usage with deliberate capability. This guide gives you the phases to build one.

> Capability building is not a training catalog. It is a sequenced program with targets, owners, delivery mechanisms, and measurement — built on top of [role redesign](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/03-role-redesign-methodology.md) and feeding the [talent-readiness assessment](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/05-assessment-talent-readiness-scoring.md).

---

## Phase 0 — Baseline and Target-Set

Before designing any program, establish two things:

- **Where people are.** Run the [talent-readiness assessment](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/05-assessment-talent-readiness-scoring.md) to baseline current literacy by role and population. Expect the Work Trend Index pattern locally — high usage, low training, lots of BYOAI *(Microsoft & LinkedIn, 2024)*.
- **Where they need to be.** Pull the capability deltas from [role redesign](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/03-role-redesign-methodology.md). Set differentiated targets: the broad workforce to **Fluency (Level 2)**, a meaningful minority to **Builder (Level 3)**, and a small core at **Architect (Level 4)**.

The output is a simple matrix — population × current level × target level × deadline — that the rest of the roadmap fills in. Note the regulatory floor: the **EU AI Act's Article 4 AI-literacy obligation has applied since 2 February 2025**, so a baseline-awareness program for anyone touching AI systems is a compliance requirement, not just good practice *(European Commission, EU AI Act, 2024)*.

---

## Phase 1 — Foundational AI Literacy (Everyone)

The first program is universal and shallow: bring the entire workforce to **Awareness**. Cover what generative AI is and is not, the failure modes (hallucination, data leakage, bias), responsible-use and data-handling rules tied to your [governance policy](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-ai-policy-and-acceptable-use.md), and a first hands-on session with the sanctioned tools.

Keep it short, mandatory, and role-agnostic. The goal is a common floor and a common vocabulary, not expertise. This phase also satisfies the EU AI Act Article 4 obligation for staff operating AI systems *(European Commission, EU AI Act, 2024)*.

---

## Phase 2 — Applied Fluency (Most Knowledge Workers)

This is the phase that produces most of the value, and it cannot be delivered by a generic course. Fluency is domain-specific — a marketer, an analyst, and a support agent need different prompts, examples, and workflows. Design it as **function-specific, hands-on, and anchored in real tasks** drawn from the [workflow](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md) and role-redesign work.

Treat "prompt engineering" as a *general literacy*, not a specialist track. The standalone prompt-engineer role collapsed precisely because strong prompting became an expected baseline skill rather than a separate job *(TechRepublic, 2025)* — so teach prompting, verification, and calibrated trust to everyone in the fluency program rather than concentrating it in a few specialists. Reinforce that augmentation lifts less-experienced workers most (the ~34% novice gain in the support-desk study), which makes fluency programs especially high-leverage for early-career and frontline staff *(Brynjolfsson, Li & Raymond, "Generative AI at Work," 2023)*.

---

## Phase 3 — Builders and Specialists

A smaller program develops the **Builder** layer — people who compose agents, automations, and retrieval workflows on top of the [platform](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md). Builders are the multiplier between the specialist core and the fluent majority; under-investing here leaves the platform unused. Select for aptitude and interest surfaced in Phases 1–2, give them deeper hands-on training and sandboxed build time, and connect them to the architect/specialist core.

For the **Architect/specialist** layer, capability is usually closed by **hiring and partnering** rather than internal development, because the depth required is too slow to grow from scratch — and because the market premium for that talent is steep (**a 56% wage premium for AI skills**) *(PwC, Global AI Jobs Barometer, 2025)*.

---

## Phase 4 — Champions Network and Communities of Practice

Programs deliver the baseline; **champions sustain and diffuse it.** Stand up a network of practitioners — one or more per function — who are a level ahead and who coach peers, surface working use cases, and translate central guidance into local language. This is the same engine the [adoption program](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/03-practitioner-guide-designing-an-adoption-program.md) relies on, and it is the answer to the training gap: when 75% use AI but only 39% are formally trained *(Microsoft & LinkedIn, 2024)*, peer-to-peer diffusion is already how most learning happens — the champions network makes it deliberate and good rather than accidental and uneven.

Support champions with a community of practice: a recurring forum, a shared prompt-and-pattern library, and visible recognition. Decide your operating model — a central **center of excellence**, a **federated** champion model, or a hybrid — and resource it; champion time must be real and protected, not volunteered on top of a full job.

---

## Phase 5 — Build, Buy, or Partner for Delivery

Each program above can be delivered three ways, and the choice should be explicit per layer:

- **Build (in-house).** Best for fluency, which must be tailored to your functions and tools. Generic courses underperform here.
- **Buy (off-the-shelf training and certification).** Efficient for the universal awareness floor and for standardized technical curricula. Large enterprises have committed at scale — Amazon's **Upskilling 2025 pledged more than $1.2 billion to provide skills training to 300,000 employees** (up from an initial $700 million for 100,000 in 2019) *(Amazon, Upskilling 2025, 2021)* — but spend is not the point; *fit and follow-through* are.
- **Partner (external providers and integrators).** Best for the specialist/architect layer and for accelerating early phases while internal capability is still thin.

The governing rule from the framework holds: **build the broad middle, hire the deep core, partner for the spikes and the bridge.**

---

## Measuring the Roadmap

Track capability the way you track any program — against the baseline, on a cadence:

- **Coverage** — share of each population that has reached its target literacy level (re-run the [assessment](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/05-assessment-talent-readiness-scoring.md)).
- **Application** — is trained capability showing up as changed work? Cross-reference [adoption](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/04-assessment-adoption-maturity-scoring.md) and [workflow](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md) metrics; training that does not change behavior is waste.
- **Outcomes** — does capability connect to value? Tie back to the [measurement track](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/02-measurement-framework.md).

---

## Checklist

- [ ] Baseline run and capability deltas pulled from role redesign (population × current × target × deadline matrix)
- [ ] Phase 1 universal awareness program live and mandatory (satisfies EU AI Act Article 4)
- [ ] Phase 2 fluency program built **function-specific and hands-on**, with prompting taught as general literacy
- [ ] Builder track selecting and developing the multiplier layer; architect/specialist gaps closed by hire/partner
- [ ] Champions network and community of practice stood up, with **protected** champion time
- [ ] Build/buy/partner decided explicitly per layer
- [ ] Coverage, application, and outcome metrics defined and on a cadence

---

## Key Takeaways

- **Replace BYOAI with a roadmap.** 75% use AI, only 39% are trained, and 78% bring their own tools — ungoverned by default *(Microsoft & LinkedIn, Work Trend Index, 2024)*.
- **Sequence by layer:** universal awareness → function-specific fluency → builders → champions, each with differentiated targets.
- **Fluency is domain-specific and where the value is**; teach prompting as a general literacy, not a specialist role *(TechRepublic, 2025)*.
- **Champions make peer diffusion deliberate** — the realistic answer to a 75%/39% usage-training gap *(Microsoft & LinkedIn, 2024)*.
- **Build the broad middle, hire/partner the deep core.** Scale spend (e.g. Amazon's $1.2B for 300,000) matters less than fit and follow-through *(Amazon, Upskilling 2025, 2021; PwC, Global AI Jobs Barometer, 2025)*.
- **Measure coverage, application, and outcomes** — training that does not change work is waste.
