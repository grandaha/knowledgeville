# AI-Assisted Software Development

Every other bundle here is written for a leader, a manager, or a knowledge worker deciding
what to do *about* AI. This one is written for the developer actually doing it — building
software with an AI coding agent, day to day, and needing a straight answer to two
questions the hype cycle keeps blurring together: does this actually make me faster, and
what does it expose me to that I was not exposed to before.

Both questions have real, rigorous evidence behind them now, not just vendor claims and hot takes. A randomized controlled trial found experienced developers took 19% *longer* with AI tools than without. They still believed afterward that AI had made them roughly 20% faster ([METR, 2025](#ev-metr-2025-early-ai-experienced-os-dev-productivity)).

Separately, AI coding agents have already been hit by named, documented attacks. A real, patched vulnerability exists in Claude Code. A malicious repository could exfiltrate a user's API keys before the trust prompt was ever shown ([Check Point Research, 2026](#ev-checkpoint-2026-claude-code-key-exfiltration-cve)). A supply-chain campaign has hidden invisible Unicode characters inside AI assistant config files. It triggers a fake "security scan" that exfiltrates developer secrets ([Socket Research Team, 2026](#ev-trapdoor-2026-ai-assistant-config-poisoning)). Neither of those facts is hypothetical, and neither is well served by a consultancy's portfolio framework.

See [The Two Real Questions](/ai-assisted-software-development/framework-architecture.md)
for how the bundle's two tracks — productivity and security — relate to each other.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **METR — *Measuring the Impact of Early-2025 AI on Experienced Open-Source Developer Productivity*, 2025.** When developers are allowed to use AI tools, they take 19% longer to complete issues. Developers had anticipated a 24% speedup before using AI. After experiencing the slowdown firsthand, they still believed AI had accelerated their work by approximately 20%. [View source](https://metr.org/blog/2025-07-10-early-2025-ai-experienced-os-dev-study/){#ev-metr-2025-early-ai-experienced-os-dev-productivity} · verified 2026-07-06 · primary
- **Check Point Research — *Caught in the Hook: RCE and API Token Exfiltration Through Claude Code Project Files*, 2026.** If a user started Claude Code in an attacker-controlled repository. The repository included a settings file that set ANTHROPIC_BASE_URL to an attacker-controlled endpoint. Claude Code would issue API requests before showing the trust prompt. [View source](https://research.checkpoint.com/2026/rce-and-api-token-exfiltration-through-claude-code-project-files-cve-2025-59536/){#ev-checkpoint-2026-claude-code-key-exfiltration-cve} · verified 2026-07-06 · primary
- **Socket Research Team — *TrapDoor Crypto Stealer Supply Chain Attack Hits 34 Packages*, 2026.** One of the more unusual features in TrapDoor is its use of AI-targeted injection through files such as .cursorrules and CLAUDE.md. The attacker attempts to plant hidden instructions using zero-width Unicode characters. The campaign spans more than 34 malicious packages and 384+ related versions and artifacts across npm, PyPI, and Crates.io. [View source](https://socket.dev/blog/trapdoor-crypto-stealer-npm-pypi-crates){#ev-trapdoor-2026-ai-assistant-config-poisoning} · verified 2026-07-06 · primary

## In this section

| Page | Last updated |
| --- | --- |
| [The Two Real Questions](framework-architecture.md)<br>How this bundle is organized: whether AI coding agents actually help, and how to secure the workflow they create. | Updated 2026-07-06 |
| [Does AI Coding Actually Help?](01-does-ai-coding-actually-help/)<br>The real, unresolved evidence on whether AI coding agents make developers faster — and what that means for how you use them. | Updated 2026-07-06 |
| [Securing the AI Coding Workflow](02-securing-the-coding-workflow/)<br>The real attack surface AI coding agents introduce — named vulnerabilities, documented campaigns — and how to defend against it. | Updated 2026-07-06 |
| [Glossary](glossary.md)<br>Plain-language definitions of the terms used across this bundle. | Updated 2026-07-06 |
| [Validation](validation/)<br>How this bundle is validated — sourced claims are checked and each sweep is recorded here. | Updated 2026-07-06 |
