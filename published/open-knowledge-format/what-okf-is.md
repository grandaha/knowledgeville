---
type: Concept
title: What OKF Is
description: A plain-language introduction to the Open Knowledge Format and why a format for knowledge is worth caring about.
resource: "https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md"
tags: [okf, open-knowledge-format]
timestamp: "2026-07-01"
---

The Open Knowledge Format (OKF) is an open format for representing *knowledge* — the context, judgment, and curated insight around your data and systems. It is written so both people and AI agents can read it. Its own definition calls it "an open, human- and agent-friendly format for representing knowledge" ([OKF spec, 2026](#ev-okf-spec-v01-definition)).

The surprising part is how little there is to it. An OKF bundle is a directory of markdown files with a few lines of structured metadata at the top of each one. There is no database, no schema registry, and no special tool you must install. As the specification puts it, if you can `cat` a file, you can read OKF ([OKF spec, 2026](#ev-okf-spec-v01-definition)).

## Why a format for knowledge matters

Most organizational knowledge lives in places that do not travel well: wikis, slide decks, scattered documents, and people's heads. It is hard to move, hard to trust, and hard for a machine to use. A format changes that. Write knowledge to a shared, portable structure and the same body of work travels. A colleague can read it, a new hire can inherit it, or an AI assistant can be pointed at it. You do not rebuild it each time.

This matters more now that the reader is often an agent. An AI assistant handed a pile of raw documents has to guess at what is authoritative and where a claim came from. Knowledge written to a format carries that structure with it. That is the shift this bundle is really about: knowledge you can publish once and let both people and machines consume.

Knowledgeville itself is built on OKF, so this bundle is also us describing the format we use every day.

## How to read this bundle

This bundle is written for knowledge and strategy leaders, not for engineers implementing the spec. It comes in two arcs.

**[Understanding OKF](/open-knowledge-format/01-understanding-okf/index.md)** covers the format as it stands today. It shows how the model works, where it fits against the alternatives you know, and how it handles where a claim came from.

**[The Potential](/open-knowledge-format/02-the-potential/index.md)** is our grounded read of where this is heading. It asks why a format matters when an agent reads, where OKF could go next, and whether the direction fits you.

One honest note on sourcing. Where this bundle states what OKF *is*, it is grounded in the canonical specification. Where it argues about what OKF *could become*, that is our analysis — informed by real signals, but a point of view, not settled fact. We mark the difference as we go.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Open Knowledge Format specification — *OKF SPEC.md (GoogleCloudPlatform/knowledge-catalog)*, v0.1.** an open, human- and agent-friendly format for representing knowledge; If you can cat a file, you can read OKF. [View source](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md){#ev-okf-spec-v01-definition} · verified 2026-07-01 · primary
