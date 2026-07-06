---
type: Concept
title: Protecting Your Repo and Secrets
description: "Practical defenses: reviewing agent config file changes, scoping credentials and tool access, and catching tampering early."
tags: [ai-assisted-software-development, security]
timestamp: "2026-07-06"
---

Each of these defenses answers a specific attack from [The Real Attack Surface](/ai-assisted-software-development/02-securing-the-coding-workflow/the-real-attack-surface.md) — this is not a generic security checklist.

## Review agent config file changes like a dependency update

TrapDoor hid its instructions inside `.cursorrules` and `CLAUDE.md` files using zero-width Unicode characters. Those characters are invisible in a normal editor, but an AI assistant still reads and acts on them regardless ([Socket Research Team, 2026](#ev-trapdoor-2026-ai-assistant-config-poisoning)). Treat a change to any file an AI agent reads automatically the same way you would treat a change to a dependency. It is something to diff and read before merging, not something that gets a pass for being "just config." A diff tool that renders invisible Unicode visibly, or a pre-commit check that flags non-printable characters, catches this specific technique directly.

## Keep the agent patched, and control where it can send data

CVE-2026-21852 worked because Claude Code issued API requests carrying credentials before a user had approved the repository at all ([Check Point Research, 2026](#ev-checkpoint-2026-claude-code-key-exfiltration-cve)). It is fixed as of version 2.0.65, so the first defense is simply running a current version. Patching does not end the category of risk, though. Any agent that can read a project's own network configuration before establishing trust can be redirected the same way. Pin or allowlist the endpoints an agent is allowed to call. Run agents against unfamiliar repositories inside a sandbox or container with controlled network egress, rather than your normal environment with full credentials. Scoped, short-lived tokens are still worth using over long-lived API keys, but scoping only limits the damage after a leak. It does not stop the leak the way patching and egress control do.

## Control what the agent can execute, not just what it reads

Every attack in this bundle ends the same way. The agent takes an action, a network call or a shell command, that a human never approved. Reading defenses like reviewing config files and scoping credentials address how the bad instruction gets in. They do not address what happens when the agent tries to act on it. Run agents with the narrowest shell and network permissions the task actually needs. Require explicit approval before an agent runs a command it has not run before in that session. An agent that can open pull requests or send messages on your behalf earns the same review discipline as a new engineer's first commits.

## Watch for the tells of a compromised config

A few concrete, checkable signs are worth watching for. A config file that changed recently with no explained commit message. A settings file that redirects a base URL, endpoint, or API host somewhere unfamiliar. A dependency added specifically because an AI agent suggested it, one you have not independently checked. None of these require deep security expertise. They require actually looking, which is the step both documented attacks in this bundle depended on someone skipping.

## A minimal checklist

Before opening an AI coding agent in a new or unfamiliar repository, read every file it will load automatically — `CLAUDE.md`, `.cursorrules`, or equivalent — before starting a session, not after. Confirm what credentials and environment variables it can access, and scope them down where you can. Diff any change to those config files the same way you would review a pull request, watching specifically for non-printable characters. Do not treat "the agent did something surprising" as a quirk to shrug off. Treat it as the first observable sign of the kind of compromise this bundle documents.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Socket Research Team — *TrapDoor Crypto Stealer Supply Chain Attack Hits 34 Packages*, 2026.** One of the more unusual features in TrapDoor is its use of AI-targeted injection through files such as .cursorrules and CLAUDE.md. The attacker attempts to plant hidden instructions using zero-width Unicode characters. The campaign spans more than 34 malicious packages and 384+ related versions and artifacts across npm, PyPI, and Crates.io. [View source](https://socket.dev/blog/trapdoor-crypto-stealer-npm-pypi-crates){#ev-trapdoor-2026-ai-assistant-config-poisoning} · verified 2026-07-06 · primary
- **Check Point Research — *Caught in the Hook: RCE and API Token Exfiltration Through Claude Code Project Files*, 2026.** If a user started Claude Code in an attacker-controlled repository. The repository included a settings file that set ANTHROPIC_BASE_URL to an attacker-controlled endpoint. Claude Code would issue API requests before showing the trust prompt. [View source](https://research.checkpoint.com/2026/rce-and-api-token-exfiltration-through-claude-code-project-files-cve-2025-59536/){#ev-checkpoint-2026-claude-code-key-exfiltration-cve} · verified 2026-07-06 · primary
