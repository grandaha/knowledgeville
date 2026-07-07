---
type: Concept
title: Asking Good Analytical Questions
description: "How the shape of the question you ask determines whether AI does real analysis or produces a vague summary."
tags: [ai-assisted-data-analysis, analysis-technique]
timestamp: "2026-07-06"
---

## The difference between a summary request and an analytical question

A summary request asks the model to describe what is already visible in the data. An analytical question asks it to derive something that is not visible without work: a comparison, a trend, a specific number computed from other numbers. The two requests can sound similar. Only one of them forces the model to do anything beyond restating what it already read.

"Tell me about this data" is a summary request, however the sentence is phrased. It invites a general description with no fixed answer to check against. "What changed between these two periods, and by how much" is an analytical question. It has one correct answer, computable from the data itself, that a person could check by hand.

## A before-and-after example

Before: "Can you look at this sales file and tell me what stands out?" This produces a plausible-sounding list of observations. Some of them may be real. Nothing in the answer tells you which ones, or how the model decided what counted as standing out.

After: "Which product category had the largest percentage change in revenue between Q1 and Q2, and what was that percentage?" This produces one specific, checkable claim. As [Code Interpreters vs. Plain Chat](/ai-assisted-data-analysis/01-getting-your-data-in/code-interpreters-vs-plain-chat.md) covers, a tool running real code against the whole file can show you the calculation. If it is not, a vague answer to the same question will not expose that gap. A specific one usually will. A model guessing at an answer rarely lands on the same exact percentage a real computation would produce, which is the tell.

The shift between the two questions is not about politeness or detail. It is about giving the model one clear target instead of an open invitation to describe.

## Questions that force the model to show its work

A follow-up question does more work than a better-phrased first question. After any analytical answer, ask what the underlying numbers were, not just the conclusion. Ask which rows or records it used to reach that answer. Ask what it would have found if a specific input changed. A model that generated the answer through real computation can usually recompute it under a changed assumption. A model that pattern-matched the answer often cannot.

This habit connects directly to the verification problem [Why Dumping a File Rarely Works](/ai-assisted-data-analysis/01-getting-your-data-in/why-dumping-a-file-rarely-works.md) opened this bundle with. A good analytical question does not just produce a better answer on its own. It produces an answer specific enough that a follow-up question can actually test it.
