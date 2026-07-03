---
type: Concept
title: Data Readiness Is a Use-Case Property
description: "Data readiness is a property of the path a use case touches, not an estate-wide gate. How to place a use case on that path."
tags: [data-readiness, ai-readiness, use-case-scoping]
timestamp: "2026-07-03"
lead: true
---

Most data readiness programs start with the same question: how clean, governed, and
well-documented is our data, across the estate? That question assumes readiness is a
property of the organization — a bar you clear once, before any AI work starts. It is not.
Readiness is a property of **the specific data path a use case touches**. A use case that
never reaches a system of record needs almost none of it. A use case that reads and writes
against one needs most of it. Scoring the whole estate before asking which use case you're
actually building answers the wrong question first.

## The diagnostic: does the use case route around the system of record, or through it?

Before assessing anything, place the use case on one axis.

- **Around the system of record** — the AI works from unstructured input, a human reviews
  the output before it ships, and nothing it touches is the enterprise's authoritative
  record of an entity (a customer, an account, a transaction). Think: drafting from a
  brief, summarizing a document, answering from public information.
- **Through the system of record** — the AI reads or writes structured data that some other
  system treats as the authoritative answer, and a real decision or action rides on it.
  Think: looking up an account, computing a balance, updating a record.

This is not a judgment about how sophisticated the use case is. A use case can be
technically impressive and still route around every system of record, and a use case can
look mundane and still touch one directly. The axis asks one question only: **if this
answer is wrong, does something authoritative downstream believe it anyway?**

## One use case, traced through the axis

The same team ships two AI-assisted tasks in the same quarter.

**Drafting the monthly customer newsletter from a one-line brief.** The AI writes from a
prompt, touches no account or transaction data, and a human reads it before it sends —
routing *around* the system of record. Readiness need: close to none, because the path has
nothing to get wrong that the review step would not catch, and no authoritative record sits
on the other end of it. A readiness program is not the blocker here; ship it.

**Handling an inbound billing question.** A customer emails asking why their invoice went
up, and the AI reads their account and invoice history to answer. That data lives in the
billing system, the system of record for what the customer owes, so this one routes
*through* it — and the readiness need is real. At minimum, the lookup has to resolve to the
right account. Entity resolution matters here, because a customer can exist as more than
one record in a system nobody has fully deduplicated, and pulling the wrong "Acme" produces
a confident, wrong answer. The lookup also needs scoped, permissioned read access, so this
task can see this customer's billing history and nothing else.

Two use cases, same quarter, same team, two different readiness answers — because the
answer follows the path, not the org.

## Where the bar keeps rising

The billing example above assumed a human reads the AI's reply before it goes out. Now
give the same agent the ability to issue the credit and update the account itself, with no
human in the loop first. The path has not changed — it is still through the system of
record — but the requirement on that path just went up again: write access scoped to
exactly what the agent may change, freshness (a credit computed against a stale balance is
a wrong credit), and a lineage trail for every action it takes, because now there is no
reviewer to catch a mistake before it reaches the customer's account.

That second jump is not a data-readiness question. It is an autonomy question, and this
bundle already has a model for it: [The Four Levels of Workflow AI
Integration](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md)
tracks exactly how oversight requirements rise as a workflow moves from human-in-the-loop
to autonomous. Use that page to place a use case's autonomy level. Use this one to place
its data path. Readiness is what the two together demand: a use case that's both *through*
the system of record and running at the higher end of the Four Levels carries the highest
readiness bar this track describes; a use case that's *around* the system of record
carries close to none, no matter how autonomous it is.

## How to use this

Before opening any page in this framework, place the use case in front of you:

1. **Does it route around or through a system of record?** If around, most of what follows
   in this framework does not apply to this use case — move on to actually shipping it.
2. **If through, how autonomous is it?** Check [The Four
   Levels](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/03-the-four-levels-of-workflow-ai-integration.md)
   for where it sits.
3. **Read the framework for what that combination needs.** [Lineage & Metadata](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata.md)
   and [Access & Integration](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/04-access-and-integration.md)
   carry the requirements that rise fastest as autonomy climbs on a through-path use case.
   [Data Governance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/03-data-governance.md)
   and [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md)
   round out what the path needs once you know it needs anything at all.

A readiness assessment that cannot answer "which use case, on which path, at what
autonomy" before it starts scoring is assessing the wrong thing.
