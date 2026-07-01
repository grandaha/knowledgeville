---
type: Concept
title: How OKF Works
description: "Bundles, concepts, and provenance — the OKF model at a leader's altitude."
resource: "https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md"
tags: [okf, model]
timestamp: "2026-07-01"
---

The Open Knowledge Format (OKF) is a way to store knowledge as plain text files. It is built so that both people and software agents can read it without special tools. You do not need to understand the spec to reason about it, because the whole model rests on two ideas: a bundle and a concept.

## What a bundle is

A bundle is a self-contained collection of knowledge. It can be a git repository, a single downloadable archive, or a subdirectory inside a larger project. The form does not matter. What matters is that everything a reader needs travels together in one place.

A bundle is the unit you share, publish, or hand to someone else. It carries everything the reader needs in one place, so nobody has to chase down separate links.

## What a concept is

A concept is one idea, written in one file. Each file has two parts: a short header of structured fields at the top, and the written content below it. The header holds the facts about the page. The content is the page itself, written in plain markdown.

One file equals one concept. This keeps each idea small enough to read in a sitting and easy to find later.

## The one required field

Every concept must declare its `type`. That is the only field OKF demands ([OKF spec, 2026](#ev-okf-spec-v01-model)). The type tells a reader what kind of page they are looking at, such as a concept, a reference, or a guide.

Other fields are recommended but optional: a title, a description, a source link, tags, and a date. You may also add your own fields when you need them. A reader that does not recognize a field must ignore it and move on, so no producer is ever locked out by another producer's choices.

## How the pieces link

Concepts point to each other with ordinary markdown links. Each concept has an ID, which is its file path inside the bundle with the `.md` ending removed. A page at `tables/users.md` has the ID `tables/users`, and that is what other pages link to.

The link itself does not carry meaning about the relationship. If one concept depends on another, or contradicts it, or extends it, you state that in the sentence around the link. The prose explains the connection; the link only makes the jump. Where a claim needs a source, that is [a matter of provenance](/open-knowledge-format/01-understanding-okf/03-provenance-and-trust.md), which OKF handles with a light convention.

## Why it stays this small

OKF is deliberately small, and that is the answer to the question a leader actually asks. There is no schema registry to maintain, no central authority to clear changes through, and no required tooling to install. If you can open a text file, you can read OKF ([OKF spec, 2026](#ev-okf-spec-v01-definition)).

That smallness is what makes the knowledge portable. A format with fewer rules survives longer, moves between systems more easily, and stays readable by both your team and the agents working alongside them. That restraint is deliberate: every rule left out is one less thing that can break, expire, or lock your knowledge inside one vendor's product.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Open Knowledge Format specification — *OKF SPEC.md (GoogleCloudPlatform/knowledge-catalog)*, v0.1.** type is the only required field; a # Citations heading with numbered references; OKF references [domain schemas such as Avro, Protobuf, OpenAPI]; it does not subsume them. [View source](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md){#ev-okf-spec-v01-model} · verified 2026-07-01 · primary
- **Open Knowledge Format specification — *OKF SPEC.md (GoogleCloudPlatform/knowledge-catalog)*, v0.1.** an open, human- and agent-friendly format for representing knowledge; If you can cat a file, you can read OKF. [View source](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md){#ev-okf-spec-v01-definition} · verified 2026-07-01 · primary
