---
type: Reference
title: Glossary
description: Plain-language definitions of the terms used across this bundle.
tags: [glossary, reference]
timestamp: "2026-07-06"
appendix: true
---

Plain-language definitions of the terms this bundle uses. It grows as the bundle does.

**Context window** — the amount of text an AI model can hold in a single conversation at once, measured in tokens. A file larger than the remaining context window cannot fit whole; what happens to the rest depends on the tool, and is not always visible to the user. See [Why Dumping a File Rarely Works](/ai-assisted-data-analysis/01-getting-your-data-in/why-dumping-a-file-rarely-works.md).

**Code interpreter** — a mode some AI tools offer where the model writes and runs real code (typically Python) against an uploaded file, rather than only reading the file's text into its context. Running real code makes an answer auditable in principle, since there is a trace to check — it does not by itself guarantee the answer is correct. See [Code Interpreters vs. Plain Chat](/ai-assisted-data-analysis/01-getting-your-data-in/code-interpreters-vs-plain-chat.md).

**Data fabrication** — an AI model producing a specific number, data point, or statistic that does not actually appear in the source data, stated with the same confident phrasing as a correct figure. See [Where AI Fabricates Data and Numbers](/ai-assisted-data-analysis/02-doing-the-analysis/where-ai-fabricates-data-and-numbers.md).

**Repeatable method** — an analysis approach documented well enough, and tested on more than one dataset, that it produces reliable results on a new dataset rather than depending on that dataset's particular quirks. See [Building a Method, Not a Lucky Prompt](/ai-assisted-data-analysis/03-making-it-repeatable/building-a-method-not-a-lucky-prompt.md).
