---
type: Concept
title: Why Your AI Gives Three Different Answers
description: A working note on shared definitions — why the same question returns different numbers, and how much semantic modeling is actually worth doing.
tags: [semantics, data-governance, definitions]
timestamp: "2026-08-10"
---

!!! note "Working notes"
    Current understanding of an active question, not a finished reference. Revised as the
    research develops.

Three executives ask an AI assistant how many active customers the company has. They get three
numbers. Nobody has made an error.

Finance counts a customer as active if they have been billed in the current period. Sales counts
anyone with an open opportunity. Support counts anyone entitled to raise a ticket. Each
definition is correct for the job it was built for, and each has been correct for years. What
changed is that one system now answers all three questions from the same prompt box. A
disagreement that sat unnoticed across three reports shows up in one.

This is the problem the word *ontology* is currently sold to solve. That word covers work ranging
from a week of arguing to a multi-year program. So the useful question is how much of it to do.

## The distinction that does the work

Two very different projects share the vocabulary, and they have opposite track records.

**Agreeing on definitions for the measures you already report** has a long history of working. It
has been done under names nobody calls ontology: the chart of accounts, Business Objects
universes, LookML, dbt metrics. The work is bounded, and something reads the output every week.

**Modeling the enterprise and its relationships as one coherent structure** is the recurring
failure. Enterprise-wide master data management, the semantic web, and data fabric all promised
it. All were governed seriously, and all faded.

A plausible mechanism for the difference, and I have not found a case that tests it. A metric
definition has a consumer who notices when it breaks. Somebody reads that dashboard on Monday, and a wrong
number produces a complaint the same day. A full enterprise model serves queries that have not
been asked yet. Nothing pulls on it, the upkeep loses its budget line, and the model decays
without anyone noticing until much later.

The story would also predict things I have not checked. A metric nobody watches any more should
decay like an enterprise model. An enterprise model serving one narrow, heavily-queried slice
should hold up like a metrics layer. Until one of those is tested, this fits two known outcomes
after the fact rather than predicting a third.

Taking it at face value gives a gradient. Metric definitions, then resolving identity on a few
core entities, then modeling relationships between them, then the whole enterprise. The risk
rises at every step. Where a given organization should stop is what I could not find answered
anywhere.

## Why the sales pitch blurs the two

Almost every number available on this topic comes from someone who benefits from the answer.

Data catalog vendors gain from "agents need semantics," which lets a catalog bill against an AI
budget instead of a governance one. Consultancies gain because the definitional argument is
billable by the hour. Internally, the strongest advocate is often a data leader for whom "AI
needs this" turns a cost center into the CEO's top priority.

The skeptics have positions too. An article titled *why most enterprise ontologies fail* is rarely
an argument against doing the project. It usually argues for hiring someone who knows the way
that does not fail. Selection bias compounds this. No one writes up the boring metrics layer that
has worked for four years, so the visible record over-represents failure.

The blur matters because credibility transfers. A bounded standard for metric definitions gets
discussed alongside a platform that models your whole business. The second borrows the first's
respectability.

Open Semantic Interchange is the current example, and the detail worth knowing is how early it
is. Its first release was **v0.1**, announced in January 2026 under Apache 2.0
([Open Semantic Interchange, 2026](#ev-osi-spec-v01-release-2026)). It has since moved to the
Apache Incubator and been renamed Apache Ossie
([The Apache Software Foundation, 2026](#ev-apache-ossie-incubator-2026)). Moving governance to a
neutral foundation is a good sign. Incubation is also a starting line, and a 0.1 spec is a
proposal that platforms have agreed to look at.

That version number is worth dwelling on, because I got it wrong first. Several write-ups call it
v1.0. The spec's own version history says otherwise, and the difference between a 1.0 and a 0.1
is most of what a reader wants to know about how settled something is.

Note what it standardizes: datasets, relationships, fields and metrics, expressed in YAML
([Open Semantic Interchange, 2026](#ev-osi-spec-scope-yaml-2026)). That is metric definitions —
the bounded work with the good record. It is weak evidence for the enterprise modeling it gets
quoted alongside.

## What the three words mean, once you need them

Learn the vocabulary once you have a decision to make, not before.

- **Ontology** is the rulebook: what an entity is, what attributes it must have, what values are
  allowed, how it relates to other entities.
- **Knowledge graph** is a place that rulebook can live and be queried.
- **Semantic layer** is how definitions get exposed to whatever consumes them.

The use of this distinction is defensive. A vendor selling a platform will bundle all three and
name the bundle after whichever term is selling best that quarter. Knowing they are separable is
what lets you ask which part you are buying.

## What is new since the last time this failed

The honest steelman rests on three costs that moved, not on ontology improving.

**Writing the model got cheap.** Drafting definitions and mappings was the bottleneck that helped
kill the previous wave. Language models now produce a first draft at almost no cost, which moves
the bottleneck to deciding.

**Incompleteness stopped being fatal.** Formal reasoners of the previous era needed the model to
be correct. An inconsistent ontology broke them, so a half-finished model returned nothing.
Language models degrade gradually, so partial semantics still helps. Every real model is
permanently incomplete, so this changes the economics of the normal case.

**There is finally a consumer that reads definitions every day.** People route around bad
definitions without noticing. An analyst knows which revenue figure is meant in which meeting.
Software does not know, and it will not ask.

**The counter is serious, and I have not resolved it.** The first two changes argue for cheap,
disposable, per-use-case semantics. That is close to the opposite of the durable practice the
vendor pitch describes. It also matches what this knowledge base argues elsewhere: readiness is a
property of the specific data path a use case touches, not a company-wide state to reach first.
See
[Readiness Is a Use-Case Property](/enterprise-ai-transformation/tracks/03-data-readiness/readiness-is-a-use-case-property.md).

## The failure mode nobody reports

The likeliest bad outcome is a completed project.

Faced with a definitional argument the business will not settle, the pragmatic move is to ship
both definitions with better labels. The model now holds `active_customer_finance` and
`active_customer_sales`. Nobody lost the argument, the program delivered on schedule, and the
assistant still returns three different numbers, each now correctly attributed.

That outcome looks like success in every status report, which is why it is hard to find written
up as failure. If it is as common as the mechanism suggests, it would explain a fair share of the
"we did this and nothing changed" accounts. I am reasoning about incentives here, not reporting a
measured result.

## What the evidence does and does not show

**There is a controlled measurement, and it measures the wrong unit.** I went looking for evidence
that an agreed semantic layer improves AI output, expecting to find none. What exists is close
enough to be worth reporting and different enough that it does not settle the question.

BIRD is an academic text-to-SQL benchmark built over real databases. It supplies hand-written
notes explaining what each question means, on the explicit grounds that schema alone does not
carry the meaning a query needs ([Li et al., 2023](#ev-bird-external-knowledge-design-2023)).
Then it publishes accuracy with those notes and without them, on identical questions.

The difference is large ([Li et al., 2023](#ev-bird-external-knowledge-delta-2023)). On the development set, GPT-4 went from 30.90% to 46.35% execution accuracy, a gain of 15.45 points.
The result I did not expect is the human row of the same split ([Li et al., 2023](#ev-bird-external-knowledge-delta-2023)): people went from 72.37% to 92.96%, a gain of 20.59 points.
The annotations helped the people more than they helped the model.

That last figure is what makes the measurement worth having. If annotations helped only the
model, this would be a story about model limitations, and next year's model might close it. The
humans needed them more, which says the meaning is genuinely absent from the schema rather than
merely hard for software to infer.

Both figures above are development-set numbers, because the paper reports no human result on the
test set. The test-set model figures are higher, at 34.88% and 54.89% <!-- noev: same Table 2, cited immediately above -->.

What it does not measure is the thing being sold. BIRD's notes are written per question, by hand,
by someone who already knows the answer. An organization-wide semantic layer is a different
object: negotiated once, maintained by people who will not be in the room when it is used, and
applied to questions nobody anticipated. The 20 points establish that meaning is missing and
valuable. They do not establish that a governed layer is how you supply it.

For scale on the underlying task ([Li et al., 2023](#ev-bird-benchmark-human-gap-2023)), BIRD's headline gap at publication was 54.89% for the leading model against 92.96% for human annotators. Models have improved substantially since.

**Numbers I left out.** A widely repeated claim that only 27% of organizations <!-- noev: deliberately unsourced — the point is that this figure has no traceable instrument --> run knowledge
graphs in production came with no instrument, sample, or definition of "in production." It also
conflicts with a figure already published here, that roughly 15% report mature data governance <!-- noev: DATAVERSITY, cited in Master Data Management -->,
in [Master Data Management](/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/master-data-management.md).
The two are not strictly contradictory, but they sit oddly together, and the first gives no way
to check. A staffing rule of thumb of one full-time person per 50
to 100 entity types is a consulting heuristic, even though it is easy to budget against. Analyst
forecasts of accuracy gains by 2027 are sold by the firms that sell the research, and they are
evidence about the discourse rather than the effect.

**Still open.** Has anyone round-tripped a real metric set between two rival platforms through
the spec and got identical results? Is there a documented case, with a named organization and a
named decision-maker, where a definitional conflict was settled? Does any published result break
success out by scope, so that a number about metric definitions is not quoted to justify an
enterprise program? Absent that last one, every published number describes something other than
the decision a reader is making.

## Where this leaves me

The work worth doing is smaller than the work being sold, and it starts with people rather than
software.

If three functions report three numbers, that is a disagreement between people, and no platform
settles it. Buying infrastructure first means paying to apply an argument nobody has finished
having. Worse, whoever configures the system settles it by default — usually the data team, under
deadline, without anyone registering that a business decision was made.

I cannot support the following with a citation, but here is what I would try. Take one question
that several functions answer differently. Get the argument settled by someone with the authority
to settle it. Only then encode the result where machines read it. That is a claim about
sequencing, and it stays a note until I find someone who has done it and written it up.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Open Semantic Interchange (now Apache Ossie, incubating) — *core-spec/spec.md, Version History section (repo: apache/ossie, formerly open-semantic-interchange/OSI); the January 2026 announcement is 'OSI Specification Now Live' at open-semantic-interchange.org/updates/*, 2026.** 0.1.1 (2025-12-11): Initial release. [View source](https://open-semantic-interchange.org/updates/){#ev-osi-spec-v01-release-2026} · verified 2026-08-10 · primary
- **The Apache Software Foundation — *Apache Ossie (Incubating): The New Name for Open Semantic Interchange*, 2026.** The Open Semantic Interchange project has been accepted into the Apache Incubator under a new name — Apache Ossie (incubating). [View source](https://ossie.apache.org/updates/){#ev-apache-ossie-incubator-2026} · verified 2026-08-10 · primary
- **Open Semantic Interchange (now Apache Ossie, incubating) — *core-spec/spec.md (repo: apache/ossie, formerly open-semantic-interchange/OSI)*, 2026.** Support for datasets, relationships, fields, and metrics. [View source](https://open-semantic-interchange.org/){#ev-osi-spec-scope-yaml-2026} · verified 2026-08-10 · primary
- **Li et al. (University of Hong Kong and collaborators) — *Can LLM Already Serve as A Database Interface? A BIg Bench for Large-Scale Database Grounded Text-to-SQLs (BIRD), arXiv:2305.03111 (v3)*, 2023.** Our emphasis on database values highlights the new challenges of dirty and noisy database values, external knowledge grounding between NL questions and database values, and SQL efficiency, particularly in the context of massive databases. [View source](https://ar5iv.labs.arxiv.org/html/2305.03111){#ev-bird-external-knowledge-design-2023} · verified 2026-08-10 · primary
- **Li et al. (University of Hong Kong and collaborators) — *BIRD, arXiv:2305.03111 (v3), Table 2 — columns 'w/o knowledge' and 'w/ knowledge' for development and testing data*, 2023.** The Execution Accuracy (EX) of advanced text-to-SQL models in Bird. The human performance is also provided. [View source](https://ar5iv.labs.arxiv.org/html/2305.03111){#ev-bird-external-knowledge-delta-2023} · verified 2026-08-10 · primary
- **Li et al. (University of Hong Kong and collaborators) — *Can LLM Already Serve as A Database Interface? A BIg Bench for Large-Scale Database Grounded Text-to-SQLs (BIRD), arXiv:2305.03111 (v3, NeurIPS version of record — the arXiv abstract PAGE still renders the superseded v1 abstract, which says ChatGPT/40.08%; quote the v3 full text, not the abs page)*, 2023.** even the most effective text-to-SQL models, i.e. GPT-4, only achieve 54.89% in execution accuracy, which is still far from the human result of 92.96%. [View source](https://ar5iv.labs.arxiv.org/html/2305.03111){#ev-bird-benchmark-human-gap-2023} · verified 2026-08-10 · primary
