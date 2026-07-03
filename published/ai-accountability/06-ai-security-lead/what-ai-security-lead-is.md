---
type: Concept
title: What the AI Security Lead Is — and the Role
description: "What model-level security means, why breaches are already happening, and how this differs from a CISO's scope."
tags: [ai-security-lead, role-definition]
timestamp: "2026-07-02"
lead: true
---

This isn't a hypothetical future risk. Thirteen percent of organizations have already reported a breach of an AI model or application ([IBM, 2025](#ev-ibm-databreach-2025-ai-breach-prevalence)) — and of those breached, 97% didn't have AI access controls in place ([IBM, 2025](#ev-ibm-databreach-2025-ai-access-controls-gap)). The gap isn't exotic attackers using techniques nobody's heard of. It's organizations deploying AI without the basic controls a security review would have caught.

## What model-level security actually covers

AI security is adversarial testing aimed specifically at how AI systems can be attacked *because* they're AI systems — prompt injection, jailbreaks, data exfiltration through model outputs, and abuse of the autonomy an agentic system has been given. That's a different attack surface than the network, identity, and infrastructure security a traditional security team already owns. A model can sit behind a perfectly locked-down network and still be manipulated into leaking data or taking an action it shouldn't, through the prompt itself.

The scale of the gap is telling: of organizations that had been breached through AI, 63% either had no AI governance policy or were still developing one ([IBM, 2025](#ev-ibm-databreach-2025-ai-governance-gap)). Most AI security failures right now aren't sophisticated — they're a system shipped before anyone checked it.

## Where it sits, and who it isn't

- **CISO** owns infrastructure, network, and identity security — the traditional perimeter. You own the model itself: what happens when an attacker talks to it directly, not around it.
- **[AI Risk Officer](/ai-accountability/05-ai-risk-officer/index.md)** owns whether a model is *accurate* — validation, drift, non-adversarial failure. You own what happens when someone is *actively trying to break it*. A model can be perfectly accurate and still be trivially jailbroken.
- **[AI Governance Lead](/ai-accountability/04-ai-governance-lead/index.md)** owns policy and sign-off. You supply the technical finding — "this system is vulnerable to X" — that their review process has to act on.

There's no standardized title for this seat yet — postings use "AI Security Lead," "Head of AI Security Architecture," and others interchangeably, and frontier labs use their own terms entirely (Anthropic calls its version the Frontier Red Team, discussed in [Running a Red Team](/ai-accountability/06-ai-security-lead/running-a-red-team.md)). The function is what matters: adversarial testing of the model itself. See [The Accountability Map](/ai-accountability/the-accountability-map.md) for how this seat relates to the others.

## How this playbook is organized

- [The OWASP Top 10 for LLM Applications](/ai-accountability/06-ai-security-lead/the-owasp-top-10-for-llms.md) — the ten vulnerability categories that define what this role actually tests for.
- [Running a Red Team](/ai-accountability/06-ai-security-lead/running-a-red-team.md) — scoping an engagement, the objective-based methodology, and a worked example from a frontier lab.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **IBM (Ponemon Institute) — *Cost of a Data Breach Report 2025*, 2025.** 13% of organizations reported breaches of AI models or applications, while 8% of organizations reported not knowing if they had been compromised in this way. [View source](https://newsroom.ibm.com/2025-07-30-ibm-report-13-of-organizations-reported-breaches-of-ai-models-or-applications,-97-of-which-reported-lacking-proper-ai-access-controls){#ev-ibm-databreach-2025-ai-breach-prevalence} · verified 2026-07-02 · primary
- **IBM (Ponemon Institute) — *Cost of a Data Breach Report 2025*, 2025.** Of those compromised, 97% report not having AI access controls in place. [View source](https://newsroom.ibm.com/2025-07-30-ibm-report-13-of-organizations-reported-breaches-of-ai-models-or-applications,-97-of-which-reported-lacking-proper-ai-access-controls){#ev-ibm-databreach-2025-ai-access-controls-gap} · verified 2026-07-02 · primary
- **IBM (Ponemon Institute) — *Cost of a Data Breach Report 2025*, 2025.** 63% of breached organizations either don't have an AI governance policy or are still developing a policy. [View source](https://newsroom.ibm.com/2025-07-30-ibm-report-13-of-organizations-reported-breaches-of-ai-models-or-applications,-97-of-which-reported-lacking-proper-ai-access-controls){#ev-ibm-databreach-2025-ai-governance-gap} · verified 2026-07-02 · primary
