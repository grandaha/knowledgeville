---
type: Concept
title: Code Interpreters vs. Plain Chat
description: "What each mode actually does with your file, why running real code is necessary but not sufficient for a trustworthy answer, and the limits code interpreters have too."
tags: [ai-assisted-data-analysis, tooling]
timestamp: "2026-07-06"
---

## What each mode actually does with your file

As [What AI Is Actually Doing With Your Data](/ai-assisted-data-analysis/what-ai-is-actually-doing-with-your-data.md) covers, an AI tool can respond to your file in two structurally different ways. Plain chat reads your file into its context window and predicts a response. It works the same way it would predict the next word in any conversation. A code interpreter does something different. It writes real code and runs it against your file in a sandboxed environment, the same computation a person could run and check themselves.

Vendors do not even document the same guarantee for a similarly named feature. Anthropic's own documentation addresses format, not size. Its `document` block does not natively support Excel files at all. A spreadsheet has to be converted to plain text, or routed to the code-execution tool instead ([Anthropic, 2026](#ev-anthropic-2026-files-api-xlsx-not-native)). Google's documentation addresses the opposite question: size, not format. Its code-execution mode is capped by the same token window as plain chat. A file too large for that window returns an error rather than routing around it ([Google, 2026](#ev-google-2026-code-execution-file-limit)). Neither vendor's documentation tells you what the other vendor's does. A reader has to check both questions separately for whichever tool they are actually using.

## Why running real code is not automatically trustworthy

Running real code against a file is a genuine step up from plain chat. It replaces a guess with a computation you could, in principle, check. It is not, on its own, a guarantee that the computation is correct. A benchmark called BlueFin tested frontier models with a real code-execution tool against actual financial spreadsheets. The test environment exposed each workbook as a live, in-memory object, not a text summary ([Kundurthy et al., 2026](#ev-kundurthy-2026-bluefin-code-execution-accuracy)).

Every model tested had full tool access, and the strongest still scored below fifty percent overall. GPT-5.5 reached 49.6 percent, and Claude Opus 4.7 reached 49.2 percent, both with code execution fully enabled ([Kundurthy et al., 2026](#ev-kundurthy-2026-bluefin-code-execution-accuracy)). The failure was not whether code executed. It was in what code the model chose to write. A wrong assumption about which column holds a total produces a confidently wrong answer, and so does a formula applied to the wrong range. Either one still comes with a real, running trace behind it.

This is the distinction worth carrying forward from the rest of this bundle. Code execution answers one question: did a real computation happen. It does not answer a second, separate question: was that computation the right one. A tool passing the first test tells you nothing about the second.

## A demonstrable test you can run yourself

You do not need a benchmark to see this distinction on your own data. Give a code-execution-enabled tool a spreadsheet with a column you have already summed by hand. Ask it to compute the same total. If the code interpreter is genuinely running against your whole file, the result should match exactly, not approximately. Then ask a harder question, one requiring the tool to select the correct subset of rows first. A real filtered total or a conditional average works this way. A mismatch on the first test points back to [Why Dumping a File Rarely Works](/ai-assisted-data-analysis/01-getting-your-data-in/why-dumping-a-file-rarely-works.md), and whether the whole file even arrived. A mismatch on the second test, with the first passing, is the BlueFin finding in your own data: a real computation, still wrong.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Anthropic — *Files API*, 2026.** For file types that the document block doesn't support (for example, .docx and .xlsx), convert the files to plain text and include the content directly in your message... To analyze datasets instead of reading them as text, upload them for the code execution tool using a container_upload block. [View source](https://platform.claude.com/docs/en/build-with-claude/files){#ev-anthropic-2026-files-api-xlsx-not-native} · verified 2026-07-06 · primary
- **Google — *Code execution*, 2026.** The maximum file input size is limited by the model token window. If you upload a file that exceeds the model's maximum context window, the API will return an error. [View source](https://ai.google.dev/gemini-api/docs/code-execution){#ev-google-2026-code-execution-file-limit} · verified 2026-07-06 · primary
- **Kundurthy, Na, Moraine, Mohta, Winter, Fang, Ling, Strubell, Kirshner — *BlueFin: Benchmarking LLM Agents on Financial Spreadsheets*, 2026.** a sandboxed code execution tool exposes the workbook as an in-memory openpyxl object with restricted built-ins... frontier LLMs demonstrate poor performance on the challenging benchmark, with the strongest LLMs achieving less than 50% average scores across tasks... frontier models all struggle to clear the 50% threshold, with GPT-5.5 and Opus 4.7 at the forefront. [View source](https://arxiv.org/abs/2605.30907){#ev-kundurthy-2026-bluefin-code-execution-accuracy} · verified 2026-07-06 · primary
