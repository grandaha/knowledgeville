---
type: Concept
title: "When It Helps and When It Does Not"
description: "What the evidence implies about task type, developer experience, and codebase familiarity as the real variables."
tags: [ai-assisted-software-development, productivity]
timestamp: "2026-07-06"
---

The [productivity evidence](/ai-assisted-software-development/01-does-ai-coding-actually-help/the-productivity-evidence.md) shows two real, controlled experiments landing on opposite answers. That is not a contradiction to resolve by picking a side. It is a signal that the variables matter more than the headline number. Here is what the evidence actually supports about which variables, and how confidently.

## Task type matters more than the tool

The clearest variable comes straight out of comparing the two studies' own designs. A well-specified task built from a small starter template, with no real production codebase to learn, is close to the best case. That is where an AI coding assistant performs strongest. That is exactly what GitHub's Copilot experiment measured. Real maintenance work on a codebase with years of accumulated convention is a harder case. That is exactly what METR's experiment measured ([METR, 2025](#ev-metr-2025-familiar-codebase-and-quality-caveats)). If your day-to-day work looks more like the second than the first, do not expect the first study's number to transfer.

## Experience level cuts in a direction worth watching, not yet fully proven

AI assistance may help less-experienced developers more than experienced ones, though not yet by a quantified amount. GitHub's own Copilot study notes this in its own findings, without giving exact figures. It states: "observed heterogeneous effects show promise for AI pair programmers to help people transition into software development careers" ([Peng, Kalliamvakou, Cihon & Demirer, 2023](#ev-peng-copilot-rct-2023-55-percent-faster)). Treat it as a direction supported by early evidence, not a settled multiplier you can plug into a decision.

## Codebase familiarity as the hidden variable

As the [productivity evidence](/ai-assisted-software-development/01-does-ai-coding-actually-help/the-productivity-evidence.md) page covers, METR's developers were selected specifically for deep familiarity with their own repositories. That is a real constraint on what the study can tell you. It measures AI assistance on codebases developers already know deeply, not on unfamiliar ones. The study's own authors speculate that unfamiliarity might reverse the effect. AI could help more, not less, when a developer does not already carry an experienced maintainer's context. Nobody has run the head-to-head experiment that would confirm or kill that idea yet.

## A quick self-check

Before trusting any productivity number for your own team, ask three things about the task you actually care about:

- Is it closer to a greenfield build, or maintenance on a codebase your team already knows cold?
- Does it carry quality standards or implicit conventions a benchmark task would not have?
- Are the developers you are asking less experienced, more experienced, or a mix?

The answer changes which study's number is the more honest guess for your situation. It does not settle the question. Neither METR's nor GitHub's number was measured on your team, doing your kind of work.

## Measure it yourself instead of trusting either number

You do not need a research lab to get a real answer for your own team. Pick one recurring type of task you already do often — a bug-fix category, a routine feature shape, a maintenance chore. Track three things for a few weeks. Time from start to merged, whether it passed review without a substantive rework request, and whether it shipped a regression within two weeks. Split the work roughly in half, AI-assisted and not, for that same task type. Aim for at least 10 to 15 real instances per side, enough that one unusually hard or easy task does not decide the result.

Read the outcome honestly in both directions. If AI-assisted work is genuinely faster with no increase in rework or regressions, that is real signal, but only for the task type you measured. If it is the same speed or slower, that is real signal too, and deserves the same weight as a positive result. Watch for the one dishonest read: judging by how fast the work *felt* rather than what the numbers say. Rerun the comparison whenever the work or the tool changes shape, rather than assuming an old result still holds.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **METR — *Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity*, 2025.** experienced developers from large open-source repositories (averaging 22k+ stars and 1M+ lines of code). AI capabilities may be comparatively lower in settings with very high quality standards, or with many implicit requirements. [View source](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/){#ev-metr-2025-familiar-codebase-and-quality-caveats} · verified 2026-07-06 · primary
- **Peng, Kalliamvakou, Cihon, Demirer — *The Impact of AI on Developer Productivity: Evidence from GitHub Copilot*, 2023.** The treatment group, with access to the AI pair programmer, completed the task 55.8% faster than the control group. [View source](https://arxiv.org/abs/2302.06590){#ev-peng-copilot-rct-2023-55-percent-faster} · verified 2026-07-06 · primary
