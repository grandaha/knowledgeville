---
type: Concept
title: Where AI Fabricates Data and Numbers
description: "Documented cases of AI inventing data points and figures during data analysis specifically, not general AI hallucination, with evidence matched to the mode -- chat or code-executed -- it was actually measured in."
tags: [ai-assisted-data-analysis, verification]
timestamp: "2026-07-06"
---

## What fabrication looks like in a data context

Fabrication in a data-analysis context means the model states a specific number, row, or data point that was never in the source. It uses the same confident phrasing as a figure it actually computed. This is a different failure from the one [Silent Arithmetic and Logic Errors](/ai-assisted-data-analysis/02-doing-the-analysis/silent-arithmetic-and-logic-errors.md) covers next. An arithmetic error takes real data and computes the wrong thing. Fabrication invents a data point that does not correspond to anything in the file at all.

## Documented rates and examples

Researchers building benchmarks for exactly this kind of task have built fabrication detection directly into their evaluation taxonomies. That means the evidence here is more specific than a general hallucination statistic. CIBench, a benchmark for code-interpreter tasks, defines a distinct "Hallucination Errors" category in its own error taxonomy. It measured this category at 4.3 percent of one model's categorized errors ([Zhang et al., 2024](#ev-zhang-2024-cibench-hallucination-error-category)). That specific category covers generated code referencing undefined variables, not a model quietly reporting an invented number as though it were computed. It is a related failure, not the same one.

A study of coding agents working on time-series analysis defines a category closer to the one this page is about. It calls the category "hallucinated values": numbers introduced that are absent from the data or the code's output ([Rechtorík et al., 2026](#ev-rechtorik-2026-timeseries-hallucinated-values-not-prevalent)). The same study reports specific rates for other error categories, such as choosing the wrong analytical method. Hallucinated values do not appear among the prevalent, quantified problems it found. Fabrication is a real category researchers specifically built detection for. In this particular study, it simply did not turn out to be the dominant one.

The clearest documented instance of the mechanism itself comes from the team that built InfiAgent-DABench, a benchmark for data-analysis agents. While assembling the benchmark's own training data, GPT-4 was asked to propose code, and a separate framework actually ran it. The team found that letting GPT-4 simulate its own execution result, instead of waiting for the real one, invited exactly this kind of fabrication. They added explicit prompt instructions blocking GPT-4 from performing that simulated execution itself ([Hu et al., 2024](#ev-hu-2024-infiagent-dabench-fictitious-results)). Even a benchmark's own construction process needed a specific safeguard against this exact failure.

## A spot-check habit that catches it

Ask the model to point to the specific row or record a suspicious number came from. A number that was genuinely computed can be traced back to its source data in seconds. A fabricated number cannot be traced, because there is nothing in the file to trace it to. This habit costs one extra question. It catches a failure mode that, as the research above shows, is real but not the most common way an AI-assisted analysis goes wrong.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Zhang, Zhang, Hu, Shen, Liu, Ma, Zhou, Zhang, He, Lin, Chen — *CIBench: Evaluating Your LLMs with a Code Interpreter Plugin*, 2024.** the model generating code that contains hallucinated elements, such as utilizing undefined parameters or referencing irrelevant variables. Instruction Following Errors: 31.9%, Hallucination Errors: 4.3%, Reasoning Errors: 40.4%, and Code Errors: 23.4%. [View source](https://arxiv.org/abs/2407.10499){#ev-zhang-2024-cibench-hallucination-error-category} · verified 2026-07-06 · primary
- **Rechtorík, Dušek, Kasner — *Can LLM Coding Agents Reason About Time Series?*, 2026.** Hallucinated values: Introduced numerical values absent from data or code output. [View source](https://arxiv.org/abs/2606.16545){#ev-rechtorik-2026-timeseries-hallucinated-values-not-prevalent} · verified 2026-07-06 · primary
- **Hu, Zhao, Wei, Chai, Ma, Wang, Wang, Su, Xu, Zhu, Cheng, Yuan, Li, Kuang, Yang, Yang, Wu — *InfiAgent-DABench: Evaluating Agents on Data Analysis Tasks*, 2024.** To counter the challenge of hallucination, where GPT-4 might generate fictitious results, explicit instructions are included in the prompt to prevent GPT-4 from executing the code. [View source](https://arxiv.org/abs/2401.05507){#ev-hu-2024-infiagent-dabench-fictitious-results} · verified 2026-07-06 · primary
