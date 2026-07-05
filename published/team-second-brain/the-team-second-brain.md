---
type: Concept
title: The Team Second Brain
description: "A small team's shared, compounding knowledge base — extending Andrej Karpathy's LLM Wiki pattern from one person to a whole team."
resource: "https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f"
tags: [team-second-brain, llm-wiki, knowledge-sharing]
timestamp: "2026-07-05"
lead: true
---

A small team already has all the knowledge it needs — scattered across everyone's
individual AI chat history, one account at a time. A two-person shop and a fifteen-person
team share the same problem: each person's AI tool learns from that person alone. Nothing
compounds across the team, and nobody has an enterprise knowledge-platform budget to fix it.

## The pattern already exists — it just stops at one person

This pattern comes from Andrej Karpathy, who describes it in a gist he calls the LLM Wiki: a
large language model (LLM) "incrementally
build[s] and maintain[s] a persistent wiki — a structured, interlinked collection of
markdown files that sits between you and the raw sources"
([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-pattern-definition)). Instead of an AI tool
re-deriving an answer from scratch every time (the way most retrieval-augmented search
works), it reads new material once, folds it into the existing wiki, and keeps that wiki
current going forward. Three layers make it work: the raw sources (immutable), the wiki
itself (the LLM-maintained markdown), and a short schema file that tells the LLM how to
structure and update it.

Karpathy names the target use explicitly: "Personal... Research... Business/team... anything
where you're accumulating knowledge over time"
([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-team-scope)). Team use is not an edge case of
this pattern. It is one of the three cases Karpathy named it for.

The pattern also answers the objection a small team raises first: who has time to keep a
wiki current. Karpathy's answer is that an LLM does the keeping: "Humans abandon wikis
because the maintenance burden grows faster than the value... The wiki stays maintained
because the cost of maintenance is near zero"
([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-maintenance-cost)). A wiki a person has to
update by hand gets abandoned. A wiki an LLM updates as a side effect of normal use does not
carry that failure mode.

## Phase one, already built: an ecosystem, one person at a time

This is not a fringe pattern. A direct search of GitHub for projects built on it turns up
dozens of active repositories, several with real adoption. Khoj alone has drawn more than
35,000 stars for a free, self-hostable AI second brain
([Khoj, 2026](#ev-khoj-2026-stars)), and a cluster of projects that cite Karpathy's pattern
by name each carry thousands more, actively maintained
([nashsu/llm_wiki, 2026](#ev-nashsu-llm-wiki-2026-stars)). Every one of them is single-user.
Some make that a selling point outright: one markets itself with "zero sharing, your notes
stay yours."

Search for the team-shared version instead, and the results nearly disappear. The one
genuine attempt found is a real, well-designed system — a master brain file, persistent
memory layers, executable skills, built to work with any AI tool. It has zero stars, zero
outside contributors, and a single creator
([accountsFON/second-brain-system, 2026](#ev-accountsfon-2026-zero-traction)). Someone has
already tried to build this, thoughtfully, and it has not caught on.

## The gap: general-purpose team knowledge, not yet built for a small team

[The Single-Player Ceiling](/team-second-brain/the-single-player-ceiling.md) surveys what
people have actually built on Karpathy's specific pattern — real, popular, actively
maintained projects. Every one of them targets only a single person's own machine and
accounts, whatever topic that person feeds it.

The team layer itself is not hypothetical. Granola already runs it for one narrow input: a
team can chat across every meeting transcript in a shared folder, free, on Granola's own
Basic tier ([Granola, 2025](#ev-granola-2025-collective-brain-positioning); [Granola, 2026](#ev-granola-2026-self-serve-pricing)).
Meta is piloting an internal
team-level layer it calls Third Brain, where each employee's own workspace feeds a shared one
across dozens of teams ([Analytics at Meta, 2026](#ev-meta-analytics-2026-third-brain)). Dr.
Tali Rezun has proposed a specific architecture for exactly this: each person's own brain
stays private by default, and the shared layer holds only what a person explicitly chooses to
contribute ([Rezun & Kapusta, 2026](#ev-rezun-2026-shared-brain-architecture)).

What's still missing is the general case, self-serve, for a small team without an engineer: a
shared wiki built from everything a team's AI use touches, not just meeting transcripts, and
not an internal pilot at a company that already employs its own AI infrastructure team. This
bundle covers that general case: a team layer on top of Karpathy's pattern, built for
whatever a small team actually feeds it, not one input type.

## The same idea, turned inward

[What OKF Is](/open-knowledge-format/what-okf-is.md) makes a structural argument for why
organizational knowledge needs a format at all: "Most organizational knowledge lives in
places that do not travel well: wikis, slide decks, scattered documents, and people's heads."
That argument is about publishing knowledge outward, for other people and other agents to
read. This bundle is the same argument turned inward — a small team applying that same
discipline to its own working knowledge, before any question of publishing anything
externally ever comes up. The format problem and the team-practice problem are the same
underlying claim at two different scopes.

## How to use this bundle

Read [The Single-Player Ceiling](/team-second-brain/the-single-player-ceiling.md) next for
an honest look at what's already built and where it stops being useful for a team. Then
[Building Yours Without an Engineer](/team-second-brain/building-yours-without-an-engineer.md)
covers how a small team actually sets this up and keeps it alive, without hiring anyone to
run it.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** incrementally build and maintain a persistent wiki — a structured, interlinked collection of markdown files that sits between you and the raw sources. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-pattern-definition} · verified 2026-07-05 · primary
- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** Personal... Research... Business/team... anything where you're accumulating knowledge over time. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-team-scope} · verified 2026-07-05 · primary
- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** Humans abandon wikis because the maintenance burden grows faster than the value... The wiki stays maintained because the cost of maintenance is near zero. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-maintenance-cost} · verified 2026-07-05 · primary
- **Khoj (khoj-ai) — *khoj-ai/khoj (GitHub repository)*, 2026.** Your AI second brain. Self-hostable. Get answers from the web or your docs. [View source](https://github.com/khoj-ai/khoj){#ev-khoj-2026-stars} · verified 2026-07-05 · primary
- **nashsu — *nashsu/llm_wiki (GitHub repository)*, 2026.** LLM Wiki is a cross-platform desktop application that turns your documents into an organized, interlinked knowledge base — automatically. [View source](https://github.com/nashsu/llm_wiki){#ev-nashsu-llm-wiki-2026-stars} · verified 2026-07-05 · primary
- **Five One Nine Marketing (accountsFON) — *accountsFON/second-brain-system (GitHub repository)*, 2026.** A plug-and-play system for building a shared 'second brain' for any organization using plain markdown files. Works with any AI tool. [View source](https://github.com/accountsFON/second-brain-system){#ev-accountsfon-2026-zero-traction} · verified 2026-07-05 · primary
- **Granola (Chris Pedregal, CEO) — *Granola 2.0*, 2025.** your company's new collective brain. [View source](https://www.granola.ai/blog/two-dot-zero){#ev-granola-2025-collective-brain-positioning} · verified 2026-07-05 · primary
- **Granola — *Granola Pricing*, 2026.** AI chat within and across meetings... Shared folders for collaboration. [View source](https://www.granola.ai/pricing){#ev-granola-2026-self-serve-pricing} · verified 2026-07-05 · primary
- **Analytics at Meta — *How We Built an AI Second Brain for 60K Knowledge Workers*, 2026.** A team-level shared context system, internally called 'Third Brain', lets team members' individual workspaces feed into a shared knowledge layer. [View source](https://medium.com/@AnalyticsAtMeta/how-we-built-an-ai-second-brain-for-60k-knowledge-workers-78c507dd795b){#ev-meta-analytics-2026-third-brain} · verified 2026-07-05 · primary
- **Dr. Tali Rezun and Dražen Kapusta — *The Shared Brain: When Second Brains Start Thinking Together*, 2026.** Private brains remain private. Shared intelligence is built only from explicit contributions. [View source](https://medium.com/@talirezun/the-shared-brain-when-second-brains-start-thinking-together-0d2ad54413d9){#ev-rezun-2026-shared-brain-architecture} · verified 2026-07-05 · primary
