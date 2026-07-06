---
type: Concept
title: The Real Attack Surface
description: "The documented vulnerabilities and attack campaigns already targeting AI coding agents — named CVEs, real incidents, not hypotheticals."
tags: [ai-assisted-software-development, security]
timestamp: "2026-07-06"
---

## The CVE

An AI coding agent reads your repo and runs commands on your behalf. It has to trust that repo, at least a little, before you have had a chance to look at it yourself. CVE-2026-21852 shows what happens when that trust starts too early. Picture an attacker-controlled repository whose own settings file sets `ANTHROPIC_BASE_URL` to an attacker-controlled endpoint. Starting Claude Code there would issue API requests before ever showing the trust prompt a user would normally approve ([Check Point Research, 2026](#ev-checkpoint-2026-claude-code-key-exfiltration-cve)). That request stream could carry the user's own API key to the attacker's server. The bug was real and specific: CVSS v4.0 score of 5.3, fixed in Claude Code 2.0.65, publicly disclosed in January 2026. It is already patched, so the single most effective defense is simply running a version released after that fix. The same Check Point report also covers a separate, higher-severity vulnerability (CVE-2025-59536, an unrelated remote-code-execution bug); this section describes CVE-2026-21852 specifically. The lesson generalizes past this one tool. Any agent that reads project-level configuration before establishing trust in the project is exposed to the same class of bug.

## The config-file attack campaign

A separate, larger campaign shows the same idea used at scale. Socket's research team has been tracking a supply-chain campaign it calls TrapDoor, spanning more than 34 malicious packages across npm, PyPI, and Crates.io, aimed mainly at stealing crypto wallets and developer credentials ([Socket Research Team, 2026](#ev-trapdoor-2026-ai-assistant-config-poisoning)). One tactic inside that campaign targets AI coding tools specifically: hiding instructions inside `.cursorrules` and `CLAUDE.md` files, the config files coding agents read automatically every session, using zero-width Unicode characters. The instructions are invisible in a normal text editor. An AI assistant can still parse and act on them, triggering what looks like a routine "security scan" that actually exfiltrates local secrets.

## What the broader research shows

These two incidents are not isolated. A systematic review synthesized 78 studies of prompt-injection research against AI coding assistants, published between 2021 and 2026. It spans tools including Claude Code, Cursor, and Copilot ([Maloyan, 2026](#ev-maloyan-2026-agentic-coding-injection-sok)). Aggregated across that whole body of research, attack success rates against state-of-the-art defenses exceed 85% when adaptive strategies are used. Most published defenses stop fewer than half of sophisticated attacks. That is a meta-analysis finding, not a single measurement against any one tool. The mechanism still generalizes. Any content an agent reads and treats as instructions is a place to hide an instruction the agent will follow. A config file, a PR description, a code comment, a tool's own output — all of it qualifies.

Both incidents above are documented, named, and very likely incomplete.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Check Point Research — *Caught in the Hook: RCE and API Token Exfiltration Through Claude Code Project Files*, 2026.** If a user started Claude Code in an attacker-controlled repository. The repository included a settings file that set ANTHROPIC_BASE_URL to an attacker-controlled endpoint. Claude Code would issue API requests before showing the trust prompt. [View source](https://research.checkpoint.com/2026/rce-and-api-token-exfiltration-through-claude-code-project-files-cve-2025-59536/){#ev-checkpoint-2026-claude-code-key-exfiltration-cve} · verified 2026-07-06 · primary
- **Socket Research Team — *TrapDoor Crypto Stealer Supply Chain Attack Hits 34 Packages*, 2026.** One of the more unusual features in TrapDoor is its use of AI-targeted injection through files such as .cursorrules and CLAUDE.md. The attacker attempts to plant hidden instructions using zero-width Unicode characters. The campaign spans more than 34 malicious packages and 384+ related versions and artifacts across npm, PyPI, and Crates.io. [View source](https://socket.dev/blog/trapdoor-crypto-stealer-npm-pypi-crates){#ev-trapdoor-2026-ai-assistant-config-poisoning} · verified 2026-07-06 · primary
- **Maloyan — *Prompt Injection Attacks on Agentic Coding Assistants: A Systematic Analysis of Vulnerabilities in Skills, Tools, and Protocol Ecosystems*, 2026.** Our meta-analysis synthesizes findings from 78 recent studies (2021-2026). Attack success rates against state-of-the-art defenses exceed 85% when adaptive attack strategies are employed. We identify that most achieve less than 50% mitigation against sophisticated adaptive attacks. [View source](https://arxiv.org/abs/2601.17548){#ev-maloyan-2026-agentic-coding-injection-sok} · verified 2026-07-06 · primary
