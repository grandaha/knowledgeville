---
type: Concept
title: The Two Real Questions
description: "How this bundle is organized: whether AI coding agents actually help, and how to secure the workflow they create."
tags: [ai-assisted-software-development]
timestamp: "2026-07-06"
lead: true
---

AI coding agents raise exactly two questions that matter, and most coverage of them
answers neither honestly. This bundle is organized around those two questions, in order,
because the second one only matters once you've taken the first seriously.

## [Does AI Coding Actually Help?](/ai-assisted-software-development/01-does-ai-coding-actually-help/index.md)

The productivity story most teams operate on is vendor telemetry and adoption surveys — numbers built to justify a purchase already made. A randomized controlled trial reaches a different, uncomfortable conclusion. Experienced developers on real tasks took 19% longer with AI assistance than without it. They still believed afterward that it had made them roughly 20% faster ([METR, 2025](#ev-metr-2025-early-ai-experienced-os-dev-productivity)). That contradiction — not a settled "AI helps" or "AI hurts" verdict — is the actual state of the evidence. It changes what a reasonable team should do next. Not adopt or reject wholesale, but find which tasks and developers it helps, and check your own results instead of trusting someone else's benchmark.

## [Securing the AI Coding Workflow](/ai-assisted-software-development/02-securing-the-coding-workflow/index.md)

An AI coding agent that can read your repo, run commands, and write code is also a new target. It has already been hit, not hypothetically. A real, patched vulnerability exists in Claude Code. A malicious repository could exfiltrate a user's API keys before the trust prompt was ever shown ([Check Point Research, 2026](#ev-checkpoint-2026-claude-code-key-exfiltration-cve)). Separately, a supply-chain campaign has hidden invisible-Unicode instructions inside AI assistant config files. That is one tactic among several it uses to steal developer secrets ([Socket Research Team, 2026](#ev-trapdoor-2026-ai-assistant-config-poisoning)). This track treats that as a workflow-security problem an individual developer or small team can act on. Review what an agent reads, scope what it can touch, and know what a compromise actually looks like — not an enterprise security-team abstraction.

## Why this order

Track one establishes that the tools' core promise is contested, not proven — which means
the second track is not a tax on a settled win, it is a real cost against an uncertain
benefit. Read productivity first, security second, and the tradeoff is honest either way
you land.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **METR — *Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity*, 2025.** When developers are allowed to use AI tools, they take 19% longer to complete issues. Developers had anticipated a 24% speedup before using AI. After experiencing the slowdown firsthand, they still believed AI had accelerated their work by approximately 20%. [View source](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/){#ev-metr-2025-early-ai-experienced-os-dev-productivity} · verified 2026-07-06 · primary
- **Check Point Research — *Caught in the Hook: RCE and API Token Exfiltration Through Claude Code Project Files*, 2026.** If a user started Claude Code in an attacker-controlled repository. The repository included a settings file that set ANTHROPIC_BASE_URL to an attacker-controlled endpoint. Claude Code would issue API requests before showing the trust prompt. [View source](https://research.checkpoint.com/2026/rce-and-api-token-exfiltration-through-claude-code-project-files-cve-2025-59536/){#ev-checkpoint-2026-claude-code-key-exfiltration-cve} · verified 2026-07-06 · primary
- **Socket Research Team — *TrapDoor Crypto Stealer Supply Chain Attack Hits 34 Packages*, 2026.** One of the more unusual features in TrapDoor is its use of AI-targeted injection through files such as .cursorrules and CLAUDE.md. The attacker attempts to plant hidden instructions using zero-width Unicode characters. The campaign spans more than 34 malicious packages and 384+ related versions and artifacts across npm, PyPI, and Crates.io. [View source](https://socket.dev/blog/trapdoor-crypto-stealer-npm-pypi-crates){#ev-trapdoor-2026-ai-assistant-config-poisoning} · verified 2026-07-06 · primary
