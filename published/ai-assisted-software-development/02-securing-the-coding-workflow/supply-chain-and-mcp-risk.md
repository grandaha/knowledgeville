---
type: Concept
title: Supply Chain and MCP Risk
description: How dependency and MCP-server compromise extends the same attack surface beyond your own repo.
tags: [ai-assisted-software-development, security]
timestamp: "2026-07-06"
---

## How a poisoned dependency or MCP server extends the same attack

[The Real Attack Surface](/ai-assisted-software-development/02-securing-the-coding-workflow/the-real-attack-surface.md) covers what happens inside your own repo. The same trust problem extends to anything your agent connects to on your behalf. A Model Context Protocol (MCP) tool poisoning attack embeds malicious instructions directly inside a tool's own description. That description is invisible to the person using the agent but read and acted on by the AI model itself. Invariant Labs demonstrated this live against Cursor: a malicious MCP server's tool description silently redirected outgoing email to an attacker's address. "The agent willingly [sent] all emails to the attacker, even if the user explicitly specifie[d] a different recipient" ([Invariant Labs, 2025](#ev-invariant-labs-2025-mcp-tool-poisoning)). An academic threat-modeling paper on the wider MCP ecosystem confirms this is not a one-off demo. It names 16 distinct threat scenarios across four attacker types ([Hou, Zhao, Wang & Wang, 2025](#ev-hou-2025-mcp-threat-taxonomy)). This is a structural risk in how MCP connects agents to tools they do not independently verify.

## What has already been found

A separate, documented supply-chain campaign called PromptMink took this a step further. Instead of attacking a repository directly, it wrote fake package documentation. That documentation was engineered to make an AI coding agent recommend installing a malicious dependency on its own. Researchers describe the technique as "a combination of LLM Optimization (LLMO) abuse and knowledge injection." Researchers named the goal directly. It was "to make the LLM likely to recommend using the malicious package by making the documentation as believable as possible" ([ReversingLabs, 2026](#ev-promptmink-2026-llmo-abuse-supply-chain)). The campaign ran for seven months across more than 60 unique packages and 300 published versions. The target is the AI agent's judgment, which many developers now trust with less scrutiny than they would apply themselves.

## A trust checklist for third-party tools

Before connecting an AI coding agent to a new MCP server, read what tools it exposes and what each tool's description actually says. Read it the same way you would read a permissions request. The description itself is the attack surface, not just the tool's behavior. Prefer MCP servers you or your organization control or have reviewed over ones added casually from a marketplace or a forum recommendation. Before accepting an AI agent's dependency suggestion for a package you have not used before, verify the package independently. Check its actual maintainer history and download count. Do not trust that the agent's citation of it means it is legitimate.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Invariant Labs — *MCP Security Notification: Tool Poisoning Attacks*, 2025.** A Tool Poisoning Attack occurs when malicious instructions are embedded within MCP tool descriptions that are invisible to users but visible to AI models. The agent willingly sends all emails to the attacker, even if the user explicitly specifies a different recipient. [View source](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks){#ev-invariant-labs-2025-mcp-tool-poisoning} · verified 2026-07-06 · primary
- **Hou, Zhao, Wang, Wang — *Model Context Protocol (MCP): Landscape, Security Threats, and Future Research Directions*, 2025.** Model Context Protocol (MCP): Landscape, Security Threats, and Future Research Directions. [View source](https://arxiv.org/abs/2503.23278){#ev-hou-2025-mcp-threat-taxonomy} · verified 2026-07-06 · primary
- **ReversingLabs — *PromptMink: Claude-Targeting Crypto Malware Campaign*, 2026.** a combination of LLM Optimization (LLMO) abuse and knowledge injection. The goal is to make the LLM likely to recommend using the malicious package by making the documentation as believable as possible. [View source](https://www.reversinglabs.com/blog/claude-promptmink-malware-crypto){#ev-promptmink-2026-llmo-abuse-supply-chain} · verified 2026-07-06 · primary
