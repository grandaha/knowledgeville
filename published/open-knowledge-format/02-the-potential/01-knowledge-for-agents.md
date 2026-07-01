---
type: Concept
title: Knowledge for Agents, Not People
description: "Why a knowledge format matters when the reader is an AI agent, and the hand-it-over-via-MCP shift."
tags: [okf, agents]
timestamp: "2026-07-01"
---

The reader of your knowledge is increasingly an AI agent, not only a person. That reader does not skim or infer context the way a colleague does. This page argues our view: when the reader is an agent, the format you publish in starts to matter as much as the words.

## What changes when an agent is the reader

A person reads a document with a lifetime of context. You know your own company's style, you can tell a draft from a decision, and you can guess which page is out of date. An agent has none of that unless the knowledge carries it.

Hand an agent a folder of documents and it has to guess. It guesses what is authoritative, what is current, and where each claim came from. Those guesses are where wrong answers start. The gap is not the agent's reading skill. It is the missing structure around the words.

## Why raw documents fall short

A raw document is written for a human reader. It assumes you can judge the source, weigh the author, and notice the date at the top. Strip that judgment away and a pile of documents becomes a pile of undifferentiated text.

The agent cannot see which page supersedes another. It cannot tell a definition from an aside, or a cited fact from an offhand line. A knowledge format fixes this by carrying structure with the content. It records what kind of thing each piece is, how the pieces relate, and [where each claim came from](/open-knowledge-format/01-understanding-okf/03-provenance-and-trust.md). That structure travels with the knowledge instead of living only in a reader's head.

## The hand-it-over shift

The old way to share knowledge was to hand over a copy. You exported the documents, the other side ingested them, and both sides drifted apart from that moment on. A copy is stale the instant it is made.

MCP, the Model Context Protocol, changes the exchange. It is an open protocol that lets an AI assistant connect to an outside source and use it as a live tool. The agent does not download a snapshot. It queries the real thing.

This knowledge base is published that way. Knowledgeville is served over MCP at `https://www.onesteplabs.com/knowledgeville/mcp`. An assistant can search it, open a page with its sources attached, and see what changed, all live, without downloading anything. The agent connects to structured, sourced knowledge instead of ingesting a document dump.

## What this means for how you publish

If some of your readers are agents, publishing a folder of documents is no longer enough. The structure a person supplies in their head now has to live in the format itself. That is a change in how you publish, not only in what you write.

Our take: treat the format as part of the knowledge. Record what each piece is, how it relates to the rest, and where its claims came from. Then serve it as something an agent can query live, not a copy it has to ingest. You do not have to rebuild everything at once, but the direction is worth planning for now.
