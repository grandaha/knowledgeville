---
type: Concept
title: Provenance and Trust
description: "Why 'where did this come from' is a first-class question, and how OKF starts to answer it."
resource: "https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md"
tags: [okf, provenance]
timestamp: "2026-07-01"
---

Of everything OKF touches, provenance is the part that matters most once an agent is the reader. This page covers why, what the format gives you today, and where we have pushed past it.

## Why provenance matters more for agents

A human reader brings judgment to a claim. You see an unsourced number, sense it is off, and go check. An AI agent reading your knowledge base does none of that. It treats what it reads as fact and acts on it. So the question "where did this come from" has to be answered in the text itself, not left to the reader.

This changes what a knowledge base owes its readers. When a person is the audience, a missing citation is a gap you can fill later. When an agent is the audience, that gap becomes a confident wrong answer passed downstream. Provenance stops being polish and becomes part of the payload.

## What OKF provides today

The Open Knowledge Format is deliberately modest here. Version 0.1 asks each page to carry a `# Citations` heading with numbered references that back the claims in the body ([OKF spec, 2026](#ev-okf-spec-v01-model)). That is close to the whole of it.

Those citations can take a few shapes. A reference can be a plain URL to an outside source. It can be a bundle-relative path to another page in the same knowledge base. It can also point into a `references/` subdirectory that mirrors outside material as its own concepts. The format tells you to cite your claims and gives you room in how you do it. It does not tell you to verify them.

## How we extend it

That last gap is where Knowledgeville goes further than the spec. The base format asks you to list sources; it does not check that a source says what you claim. We treat that check as the point, so we have built practice on top of the format rather than reading it into the format.

Here is what we do. Every sourced claim lives in a small structured store, one entry per claim. Each entry is checked against its primary source before the page ships, not against a model's memory of the source. Inline citations link to that store instead of to a loose list at the bottom. A build check fails when a claim-shaped number appears with no source behind it.

None of this is required by OKF v0.1. It is what the format made possible once we decided verification was not optional. The spec gives you a place to put citations; we made those citations answer to their sources.

## What good provenance buys you

The payoff is that an agent reading your knowledge base inherits your standards, not just your words. A claim carries its source, and the source has been checked, so an agent acting on it is acting on ground you have already tested. Trust moves with the content instead of staying in your head.

For you as the owner of that knowledge, the gain is quieter and larger. You can hand the base to a reader you will never meet, human or machine. You know that each number in it can be traced back, and was. That is the difference between publishing what you believe and publishing what you can stand behind.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Open Knowledge Format specification — *OKF SPEC.md (GoogleCloudPlatform/knowledge-catalog)*, v0.1.** type is the only required field; a # Citations heading with numbered references; OKF references [domain schemas such as Avro, Protobuf, OpenAPI]; it does not subsume them. [View source](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md){#ev-okf-spec-v01-model} · verified 2026-07-01 · primary
