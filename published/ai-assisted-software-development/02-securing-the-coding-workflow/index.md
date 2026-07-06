# Securing the AI Coding Workflow

An AI coding agent that reads your repo and runs commands on your behalf has an attack
surface a plain autocomplete tool never had — and it's already been used, not just
theorized about: a real, patched vulnerability let a malicious repository exfiltrate a
Claude Code user's API keys before the trust prompt was even shown
([Check Point Research, 2026](#ev-checkpoint-2026-claude-code-key-exfiltration-cve)), and a
supply-chain campaign has used invisible Unicode instructions hidden in AI assistant config
files as one of its tactics for stealing developer secrets
([Socket Research Team, 2026](#ev-trapdoor-2026-ai-assistant-config-poisoning)). This section
starts with that documented reality, then moves to practical defense scoped to what an
individual developer or small team can actually do, and closes with the part of the attack
surface that extends beyond your own repo — the dependencies and MCP servers an agent
trusts on your behalf.

[The Real Attack Surface](/ai-assisted-software-development/02-securing-the-coding-workflow/the-real-attack-surface.md)
· [Protecting Your Repo and Secrets](/ai-assisted-software-development/02-securing-the-coding-workflow/protecting-your-repo-and-secrets.md)
· [Supply Chain and MCP Risk](/ai-assisted-software-development/02-securing-the-coding-workflow/supply-chain-and-mcp-risk.md)

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Check Point Research — *Caught in the Hook: RCE and API Token Exfiltration Through Claude Code Project Files*, 2026.** If a user started Claude Code in an attacker-controlled repository. The repository included a settings file that set ANTHROPIC_BASE_URL to an attacker-controlled endpoint. Claude Code would issue API requests before showing the trust prompt. [View source](https://research.checkpoint.com/2026/rce-and-api-token-exfiltration-through-claude-code-project-files-cve-2025-59536/){#ev-checkpoint-2026-claude-code-key-exfiltration-cve} · verified 2026-07-06 · primary
- **Socket Research Team — *TrapDoor Crypto Stealer Supply Chain Attack Hits 34 Packages*, 2026.** One of the more unusual features in TrapDoor is its use of AI-targeted injection through files such as .cursorrules and CLAUDE.md. The attacker attempts to plant hidden instructions using zero-width Unicode characters. The campaign spans more than 34 malicious packages and 384+ related versions and artifacts across npm, PyPI, and Crates.io. [View source](https://socket.dev/blog/trapdoor-crypto-stealer-npm-pypi-crates){#ev-trapdoor-2026-ai-assistant-config-poisoning} · verified 2026-07-06 · primary

## In this section

| Page | Last updated |
| --- | --- |
| [Protecting Your Repo and Secrets](protecting-your-repo-and-secrets.md)<br>Practical defenses: reviewing agent config file changes, scoping credentials and tool access, and catching tampering early. | Updated 2026-07-06 |
| [Supply Chain and MCP Risk](supply-chain-and-mcp-risk.md)<br>How dependency and MCP-server compromise extends the same attack surface beyond your own repo. | Updated 2026-07-06 |
| [The Real Attack Surface](the-real-attack-surface.md)<br>The documented vulnerabilities and attack campaigns already targeting AI coding agents — named CVEs, real incidents, not hypotheticals. | Updated 2026-07-06 |
