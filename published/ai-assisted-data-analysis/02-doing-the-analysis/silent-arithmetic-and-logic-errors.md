---
type: Concept
title: Silent Arithmetic and Logic Errors
description: "Why AI can get the math wrong on your own data even when it ran real code against the whole file, without flagging any uncertainty, and how to catch it."
tags: [ai-assisted-data-analysis, verification]
timestamp: "2026-07-06"
---

## Why arithmetic errors happen even when the tool ran real code

As [Code Interpreters vs. Plain Chat](/ai-assisted-data-analysis/01-getting-your-data-in/code-interpreters-vs-plain-chat.md) covers, running real code against a file is necessary for a trustworthy answer, but it is not sufficient. This is the sharpest version of that claim in the whole bundle. Real code, run against your real data, can still land on a wrong answer. Nothing in the output marks the difference.

[Where AI Fabricates Data and Numbers](/ai-assisted-data-analysis/02-doing-the-analysis/where-ai-fabricates-data-and-numbers.md) covers a model inventing a number with no basis in the file. This is a different failure. The data is real, and the code that ran against it is real. A model can choose the right overall approach to a problem. It can still get a detail inside that approach wrong: the wrong column, the wrong threshold, the wrong specific method for the task. The formatting, the confidence, and the level of detail look identical whether the underlying computation was right or wrong.

## Documented error rates

Three sources measure this failure in three different ways. No single number below should be read against the others directly, since each uses a different denominator. Each one, on its own terms, shows the same failure is frequent. CIBench measured how often each kind of mistake occurred across a model's errors on code-interpreter tasks. Reasoning errors reached 40.4 percent of those errors, the largest of its four categories. Hallucination, on the same model, measured only 4.3 percent of errors ([Zhang et al., 2024](#ev-zhang-2024-cibench-reasoning-error-category)).

A study of coding agents on time-series analysis supplies the mechanism behind that prevalence. One error occurred when an agent chose the right strategy but the wrong specific method or threshold within it. That single error appeared in 25 percent of code-agent answers, and 19 percent of hybrid-agent answers ([Rechtorík et al., 2026](#ev-rechtorik-2026-timeseries-wrong-method-prevalent)). The strategy was sound. The specific execution of it was not.

A financial-spreadsheet benchmark shows the ceiling this failure imposes even under close to ideal conditions. With full code execution enabled, the strongest frontier models still scored below fifty percent overall ([Kundurthy et al., 2026](#ev-kundurthy-2026-bluefin-code-execution-accuracy)). Real tool access, on real data, was not enough to clear even a coin flip.

## A quick verification habit

Pick one number from the analysis that matters enough to check, and verify it two ways. Ask the tool to recompute that specific number using a different method than the one it used the first time. Try a different formula, a different grouping, or a manual filter instead of an automatic one. Agreement between the two is real evidence. A mismatch is the exact failure this page documents, caught before it reaches a decision. Running real code bought you an answer worth checking. It never bought you an answer you could skip checking.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Zhang, Zhang, Hu, Shen, Liu, Ma, Zhou, Zhang, He, Lin, Chen — *CIBench: Evaluating Your LLMs with a Code Interpreter Plugin*, 2024.** Instruction Following Errors: 31.9%, Hallucination Errors: 4.3%, Reasoning Errors: 40.4%, and Code Errors: 23.4%. [View source](https://arxiv.org/abs/2407.10499){#ev-zhang-2024-cibench-reasoning-error-category} · verified 2026-07-06 · primary
- **Rechtorík, Dušek, Kasner — *Can LLM Coding Agents Reason About Time Series?*, 2026.** Right strategy, but wrong specific method or threshold. the strategy chosen by the agent was suitable for answering the question, but failed due to the specific method chosen within the strategy. [View source](https://arxiv.org/abs/2606.16545){#ev-rechtorik-2026-timeseries-wrong-method-prevalent} · verified 2026-07-06 · primary
- **Kundurthy, Na, Moraine, Mohta, Winter, Fang, Ling, Strubell, Kirshner — *BlueFin: Benchmarking LLM Agents on Financial Spreadsheets*, 2026.** a sandboxed code execution tool exposes the workbook as an in-memory openpyxl object with restricted built-ins... frontier LLMs demonstrate poor performance on the challenging benchmark, with the strongest LLMs achieving less than 50% average scores across tasks... frontier models all struggle to clear the 50% threshold, with GPT-5.5 and Opus 4.7 at the forefront. [View source](https://arxiv.org/abs/2605.30907){#ev-kundurthy-2026-bluefin-code-execution-accuracy} · verified 2026-07-06 · primary
