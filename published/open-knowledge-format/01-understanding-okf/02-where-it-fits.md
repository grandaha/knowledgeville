---
type: Concept
title: Where OKF Fits
description: "How OKF compares to RAG dumps, knowledge graphs, schema.org, and plain docs — and what it deliberately is not."
resource: "https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md"
tags: [okf, comparison]
timestamp: "2026-07-01"
---

OKF is not the only way to hold knowledge, and it is not always the right one. This page lines it up against the tools you already know, then states what it does not try to be.

## The alternatives you already use

You have several ways to hold knowledge, and each solves part of the problem. A RAG document dump chunks raw files and embeds them for retrieval. It is good for search, but the content stays unstructured and carries no curation or provenance. A knowledge graph models typed entities and their relationships. It is powerful for querying connections, but heavy to build, and it needs specialized tooling and upkeep.

Two more options round out the set. Structured-data vocabularies like schema.org describe things on web pages so machines can read them. That is a vocabulary, not a portable bundle you can hand to someone. Plain docs and wikis are easy for people to read, but they are not structured for machines and do not travel as a single unit.

## What OKF does differently

OKF is a minimal, portable envelope for knowledge artifacts ([OKF spec, 2026](#ev-okf-spec-v01-definition)). It is a directory of markdown files with a metadata header, readable by both people and agents. It sits close to tools you likely use: LLM wiki repositories, personal knowledge tools like Obsidian and Notion, and "metadata as code."

The difference is that OKF is specified. It writes down how a bundle is structured and how it stays interoperable. So a bundle means the same thing wherever it lands. It does this without telling you which tools to run. You get a shared format and keep your own stack.

## What OKF is deliberately not

OKF is not a knowledge graph, not a schema.org implementation, and not a standard built only for RAG. Its non-goals are stated plainly, and they matter for a fair read of where it fits ([OKF spec, 2026](#ev-okf-spec-v01-model)).

- It does not define fixed concept taxonomies. You bring your own subject matter.
- It does not prescribe storage or serving infrastructure. Where a bundle lives and how you serve it are your call.
- It does not replace domain-specific schemas such as Avro, Protobuf, or OpenAPI. OKF references them; it does not subsume them.

## When to reach for it

Reach for OKF when you need knowledge to be curated, structured, and portable as one unit, and when both people and agents will read it. It fits when you want a stable format without committing to a fixed toolset or a heavy build.

Reach for something else when your need is narrower. If you only need retrieval over raw text, a RAG store is enough. If you need rich queries over typed relationships, a knowledge graph earns its cost. If you only need to mark up web pages for machines, a vocabulary like schema.org is the right tool.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Open Knowledge Format specification — *OKF SPEC.md (GoogleCloudPlatform/knowledge-catalog)*, v0.1.** an open, human- and agent-friendly format for representing knowledge; If you can cat a file, you can read OKF. [View source](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md){#ev-okf-spec-v01-definition} · verified 2026-07-01 · primary
- **Open Knowledge Format specification — *OKF SPEC.md (GoogleCloudPlatform/knowledge-catalog)*, v0.1.** type is the only required field; a # Citations heading with numbered references; OKF references [domain schemas such as Avro, Protobuf, OpenAPI]; it does not subsume them. [View source](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md){#ev-okf-spec-v01-model} · verified 2026-07-01 · primary
