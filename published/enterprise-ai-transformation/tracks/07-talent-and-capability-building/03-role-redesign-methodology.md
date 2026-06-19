---
type: Playbook
title: "Role Redesign Methodology"
description: "A task-level methodology for mapping AI impact across job functions and redesigning roles for an augmented workforce."
tags: [talent, role-redesign, workforce, playbook]
timestamp: "2026-06-18"
---

## The Unit of Change Is the Task, Not the Job

The single most important idea in role redesign is that **AI acts on tasks, not on jobs**. Whole occupations rarely vanish; instead, the bundle of tasks that makes up a role gets rearranged — some tasks are automated away, some are augmented and done faster or better, some are untouched, and entirely new tasks appear. The foundational labor-market study of large language models found that **about 80% of the U.S. workforce could have at least 10% of their work tasks affected by LLMs, and around 19% could see at least half of their tasks affected** — an effect that spans every wage level *(Eloundou et al., "GPTs are GPTs," Science, 2024)*. The story is pervasive task-level change, not wholesale job elimination.

The WEF data shows the same shift in aggregate. Employers report that today **47% of work tasks are performed mainly by humans, 22% mainly by technology, and 30% by a human-machine combination — and expect those shares to move toward a roughly even split by 2030** *(WEF, Future of Jobs Report 2025, 2025)*. Redesign is the deliberate act of deciding, task by task, which side of that line each piece of work should fall on — rather than letting it drift, which is how [shadow AI use](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) and uneven results take hold.

> Designing for the job leads to fear ("will AI take my role?"). Designing for the task leads to action ("which of my tasks should AI do, so I can spend my time on the rest?").

This playbook gives you a repeatable method to do that decomposition and reassembly. It pairs with the [Talent & Capability Framework](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/02-talent-and-capability-framework.md) (which defines the capability the redesigned roles will need) and feeds the [capability-building roadmap](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/04-practitioner-guide-capability-building-roadmap.md) (which builds it).

---

## The Augmentation–Displacement Spectrum

Not all AI impact is the same, and conflating its forms is the root of both over-fear and over-automation. Every task sits somewhere on a spectrum:

- **Automated** — AI performs the task end-to-end with minimal human involvement (e.g. first-draft data entry, routine categorization, boilerplate generation).
- **Augmented** — AI does part of the task or assists throughout; a human still directs, judges, and owns the outcome. This is where most current value sits, and where the evidence is strongest: a field study of customer-support agents found that access to a generative-AI assistant **raised productivity by about 14% on average, with the largest gains — roughly 34% — for novice and lower-skilled workers** while having little effect on the most experienced *(Brynjolfsson, Li & Raymond, "Generative AI at Work," NBER 2023 / QJE 2025)*. Augmentation compresses the experience curve.
- **Unchanged** — tasks requiring physical presence, legal accountability, deep relationship, or judgment AI cannot yet shoulder. These often *grow* in relative importance as routine tasks are stripped away.
- **New** — tasks created by AI itself: prompting and directing systems, reviewing and verifying AI output, curating data, and governing model behavior.

The WEF frames the design goal explicitly as **augmentation — technology that complements and enhances human work rather than displacing it** *(WEF, Future of Jobs Report 2025, 2025)*. The redesign objective is to push routine tasks toward *automated*, lift skilled tasks into *augmented*, protect and expand the *unchanged* human core, and staff the *new* tasks deliberately.

---

## The Methodology: Six Steps

### Step 1 — Inventory the role as a task list

Decompose the target role into 10–30 discrete tasks, expressed as verbs with objects ("reconcile invoices," "draft client update," "triage support ticket"). Work from how the job is actually done, not the formal job description — Deloitte's research found that **63% of the work people perform already falls outside their core job description**, so the official document will mislead you *(Deloitte, The Skills-Based Organization, 2024)*. Capture rough time-share per task.

### Step 2 — Classify each task on the spectrum

For each task, assign one of the four labels — **automate, augment, unchanged, new** — using two screens: *technical feasibility* (can AI do this reliably today?) and *advisability* (should it, given risk, accountability, and relationship value?). A task can be technically automatable but deliberately kept human; record the reason.

### Step 3 — Quantify the shift

Sum the time freed by automation and augmentation. This is the redesign's raw material: the hours that, reinvested, define what the role *becomes*. Be honest that augmentation frees partial time, not whole headcount — the productivity gains are real but bounded (the ~14% support-desk figure is a useful reality check, not a promise of 14% headcount savings) *(Brynjolfsson, Li & Raymond, 2023)*.

### Step 4 — Redesign the role around the freed time

Decide what the human now does with the recovered hours. Three patterns: **deepen** (more time on the high-judgment core), **broaden** (take on adjacent work previously deferred), or **elevate** (move up to oversight, exception-handling, and AI-verification of the now-automated tasks). Write the new role as a revised task list, including the *new* tasks of directing and checking AI.

### Step 5 — Specify the capability delta

Compare the skills the redesigned role needs against what the incumbent has, mapped to the four [literacy levels](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/02-talent-and-capability-framework.md). This delta is the input to the [capability-building roadmap](/enterprise-ai-transformation/tracks/07-talent-and-capability-building/04-practitioner-guide-capability-building-roadmap.md) and to the build-vs-hire-vs-partner decision.

### Step 6 — Sequence and pilot

Do not redesign every role at once. Start with one role in one team, run it as a pilot, measure against the [workflow](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/02-workflow-optimization-framework.md) baseline, and refine the classification before scaling. Role redesign is iterative; the first task classification is always partly wrong.

---

## New Roles — and a Cautionary Tale

AI creates new roles, but they are less stable and less standalone than early hype suggested. The clearest lesson is **the prompt engineer**: touted as the breakout job of 2024 with six-figure salaries, the standalone role had largely faded by 2026 as models began to self-prompt and prompting became an expected baseline skill rather than a separate occupation *(TechRepublic, 2025)*. The skill did not disappear — it was *absorbed* into broader roles.

The design implication: **prefer absorbing new AI tasks into existing roles over creating fragile new job titles.** Durable new roles tend to cluster where AI needs human governance and orchestration — AI product managers, AI governance and risk specialists, ML and data engineers, and the **builder** layer who compose AI into workflows. Create a new title only when the task bundle is large, persistent, and genuinely distinct; otherwise, redesign an existing role to carry it.

---

## HR and Change-Management Considerations

Role redesign is an HR and trust exercise as much as an analytical one. Three considerations decide whether it lands:

- **Frame it as augmentation, transparently.** People who fear displacement disengage or hide their AI use. Anchor the conversation on tasks ("AI takes the routine parts so you do more of the work that matters"), and back the framing with the reskilling commitment — reskilling at-risk workers is generally more cost-effective than replacing them, and the large majority can transition into adjacent roles *(WEF, Future of Jobs Report 2025, 2025)*.
- **Move toward skills-based job architecture.** Static job descriptions cannot keep pace with 39% of skills changing by 2030 *(WEF, Future of Jobs Report 2025, 2025)*. Defining roles as fluid bundles of skills and tasks — the skills-based-organization model — makes redesign a routine update rather than a renegotiation *(Deloitte, The Skills-Based Organization, 2024)*.
- **Involve incumbents in their own redesign.** The people doing the work classify tasks more accurately than managers do, and co-design converts the threat narrative into ownership. This is the same psychological-safety dynamic that governs [adoption](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md).

---

## Checklist

- [ ] Target role decomposed into a concrete task list (from actual practice, not the job description)
- [ ] Each task classified: **automate / augment / unchanged / new**, with feasibility *and* advisability noted
- [ ] Freed time quantified honestly (partial-time gains, not assumed headcount cuts)
- [ ] Redesigned role written as a revised task list, including new AI-direction and AI-verification tasks
- [ ] Capability delta mapped to the four literacy levels and handed to the roadmap
- [ ] New tasks absorbed into existing roles where possible; new titles created only for large, durable, distinct bundles
- [ ] Redesign piloted in one team and measured before scaling
- [ ] Incumbents involved; change framed as augmentation; reskilling commitment made explicit

---

## Key Takeaways

- **Redesign tasks, not jobs.** ~80% of workers could see ≥10% of their tasks affected by AI, but whole-job elimination is rare *(Eloundou et al., Science, 2024)*.
- **Place every task on the augmentation–displacement spectrum** — automate, augment, unchanged, new — using both feasibility and advisability.
- **Augmentation is where today's value sits**, and it disproportionately lifts less-experienced workers (~14% average, ~34% for novices) *(Brynjolfsson, Li & Raymond, 2023)*.
- **Reinvest freed time deliberately** — deepen, broaden, or elevate — and staff the genuinely new AI-direction and verification tasks.
- **Absorb new AI work into existing roles**; the collapse of the standalone "prompt engineer" role is the cautionary tale *(TechRepublic, 2025)*.
- **Make it a skills-based, co-designed, augmentation-framed change** — static job descriptions already miss 63% of real work *(Deloitte, 2024)* and cannot track 39% skill change by 2030 *(WEF, 2025)*.
