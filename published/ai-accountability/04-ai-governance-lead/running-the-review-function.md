---
type: Playbook
title: Running the Review Function
description: "Sensitive-use triage, pre-deployment sign-off, and the ISO 42001 management-system shape, via a worked example."
tags: [ai-governance-lead, operationalization]
timestamp: "2026-07-02"
---

The framework tells you what to do. This is what a working version of it actually looks like, using Microsoft's own published practice as a concrete reference point — not because you should copy it wholesale, but because "review high-risk stuff more carefully than low-risk stuff" is easy to say and hard to run consistently without seeing a real version of it.

## Triage before you review

Not every AI use case needs the same scrutiny. Microsoft's Sensitive Uses and Emerging Technologies team exists specifically to give hands-on counseling for high-impact and higher-risk uses of AI — and to provide early guidance for novel risks and emerging capabilities before a formal policy exists for them ([Microsoft, 2025](#ev-microsoft-rai-transparency-2025-sensitive-uses)). The mechanism worth copying isn't the team's name — it's the two-speed model: a lightweight path for routine use cases, and hands-on counseling reserved for the ones that actually carry risk.

Build your own triage criteria around what "sensitive" means for your organization: decisions with legal or financial consequences for a person, novel technical capability nobody's reviewed before, or use cases that touch regulated categories of data or decisions.

## Sign off before it ships

Whatever your triage sends to the high-risk lane needs an actual gate before deployment, not a courtesy review after the fact. Microsoft applies a consistent risk-management approach across releases through pre-deployment review and red-teaming — and does it at real scale: oversight and review of every flagship model added to the Azure OpenAI Service, and every Phi model release ([Microsoft, 2025](#ev-microsoft-rai-transparency-2025-predeployment-review)). "Every" is the operative word. A pre-deployment gate that gets skipped for the releases everyone's in a hurry about isn't a gate.

## The management-system shape, if you need to formalize it

If your organization wants to certify or formalize this function rather than run it ad hoc, ISO/IEC 42001 — the world's first AI management system standard, published in 2023 and applicable to any organization that provides or uses AI-based products or services ([ISO/IEC, 2023](#ev-iso-42001-2023-definition)) — gives you the management-system shape: a documented AI policy, assigned roles and authorities, risk and impact assessment for AI systems, ongoing monitoring, and a continual-improvement loop. It's the same logic as the NIST functions, packaged as something an external auditor can certify against.

You don't need certification to run this well. But if a customer or regulator asks "how do we know your AI governance is more than a slide deck," a management system built to this shape is the answer that holds up.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Microsoft — *2025 Responsible AI Transparency Report*, 2025.** provided hands-on counseling for high-impact and higher-risk uses of AI through our Sensitive Uses and Emerging Technologies team... provided early guidance for novel risks and emerging AI capabilities, enabling innovation and incubating new internal policies. [View source](https://blogs.microsoft.com/on-the-issues/2025/06/20/our-2025-responsible-ai-transparency-report/){#ev-microsoft-rai-transparency-2025-sensitive-uses} · verified 2026-07-02 · primary
- **Microsoft — *2025 Responsible AI Transparency Report*, 2025.** continued to apply a consistent risk management approach across releases through our pre-deployment review and red teaming efforts... oversight and review of high-impact and higher-risk uses of AI and generative AI releases, including every flagship model added to the Azure OpenAI Service and every Phi model release. [View source](https://blogs.microsoft.com/on-the-issues/2025/06/20/our-2025-responsible-ai-transparency-report/){#ev-microsoft-rai-transparency-2025-predeployment-review} · verified 2026-07-02 · primary
- **ISO/IEC (JTC 1/SC 42) — *ISO/IEC 42001:2023 — AI management systems*, 2023.** ISO/IEC 42001:2023, Information technology — Artificial intelligence — Management system... the world's first AI management system standard... applicable to any organization, regardless of size, type and nature, that provides or uses products or services that utilize AI systems. [View source](https://www.iso.org/standard/42001){#ev-iso-42001-2023-definition} · verified 2026-07-02 · primary
