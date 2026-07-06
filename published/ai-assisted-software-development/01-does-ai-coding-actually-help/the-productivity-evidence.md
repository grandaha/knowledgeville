---
type: Concept
title: The Productivity Evidence
description: What rigorous research actually shows about AI coding agents and developer speed — and where it contradicts vendor telemetry.
tags: [ai-assisted-software-development, productivity]
timestamp: "2026-07-06"
---

## The vendor telemetry story

GitHub ran its own controlled experiment on Copilot: 95 professional developers, split randomly. They were asked to build an HTTP server in JavaScript from a provided skeleton codebase. The developers with Copilot access completed the task 55.8% faster than the ones without it ([Peng, Kalliamvakou, Cihon & Demirer, 2023](#ev-peng-copilot-rct-2023-55-percent-faster)). It is genuinely one of the strongest productivity results anywhere in this literature.

## What the controlled study actually found

METR ran a different experiment two years later, on a different population, doing different work. Sixteen experienced open-source developers worked on real issues, in repositories they had personally contributed to for years, using Cursor. The result: developers were 19% *slower* with AI tools than without them. Even after living through that slowdown themselves, they still believed afterward that AI had made them roughly 20% faster ([METR, 2025](#ev-metr-2025-early-ai-experienced-os-dev-productivity)).

## Why they do not measure the same thing

Both studies are real randomized experiments, not anecdotes. The difference is what they actually tested. GitHub's task was a well-specified build from a small starter template, with no real production codebase to learn. That is exactly the shape of task an AI assistant handles best. METR's developers were doing real maintenance work on codebases they already knew intimately, averaging 22,000+ GitHub stars and over a million lines of code. That work carried the kind of implicit quality standards, documentation expectations, and existing conventions a well-specified greenfield task does not have ([METR, 2025](#ev-metr-2025-familiar-codebase-and-quality-caveats)). METR's own authors flag this directly: AI capabilities may be comparatively lower in settings with very high quality standards or many implicit requirements. Neither study is wrong. They tested different kinds of work, and most real engineering work looks much more like METR's setup than GitHub's.

## What is still unresolved

METR's own authors go further and speculate that AI assistance might help *more* in an unfamiliar codebase than a familiar one. Their reasoning: an unfamiliar codebase is exactly where a developer most needs the orientation an AI assistant can provide. That is worth taking seriously, but it is a hypothesis the study's own authors raised, not something their data tested or confirmed. Nobody has yet run the controlled experiment that would actually settle it. It would need a familiar codebase against an unfamiliar one, same developers, same AI tool, measured head to head.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Peng, Kalliamvakou, Cihon, Demirer — *The Impact of AI on Developer Productivity: Evidence from GitHub Copilot*, 2023.** The treatment group, with access to the AI pair programmer, completed the task 55.8% faster than the control group. [View source](https://arxiv.org/abs/2302.06590){#ev-peng-copilot-rct-2023-55-percent-faster} · verified 2026-07-06 · primary
- **METR — *Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity*, 2025.** When developers are allowed to use AI tools, they take 19% longer to complete issues. Developers had anticipated a 24% speedup before using AI. After experiencing the slowdown firsthand, they still believed AI had accelerated their work by approximately 20%. [View source](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/){#ev-metr-2025-early-ai-experienced-os-dev-productivity} · verified 2026-07-06 · primary
- **METR — *Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity*, 2025.** experienced developers from large open-source repositories (averaging 22k+ stars and 1M+ lines of code). AI capabilities may be comparatively lower in settings with very high quality standards, or with many implicit requirements. [View source](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/){#ev-metr-2025-familiar-codebase-and-quality-caveats} · verified 2026-07-06 · primary
