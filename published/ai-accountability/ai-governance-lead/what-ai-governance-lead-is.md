---
type: Concept
title: What the AI Governance Lead Is — and the Role
description: "What this role operationalizes, why it's still finding its home in the org chart, and how it differs from the AI Risk Officer."
tags: [ai-governance-lead, role-definition]
timestamp: "2026-07-02"
lead: true
---

Ask five organizations who owns AI governance and you'll get five different answers — a privacy team, a legal department, IT, a data-governance function, an ethics office. All five are right, and that's the problem: the work is real, but the seat hasn't settled anywhere yet.

## What this role operationalizes

The AI Governance Lead turns AI policy from a document into a running practice: risk-tiering AI use cases, running sign-off gates before something ships, reviewing systems for fairness and ethical use, tracking regulatory change, and keeping the organization's AI management practices audit-ready. This is policy and process work — not model math (that's the [AI Risk Officer](/ai-accountability/ai-risk-officer/index.md)'s job) and not the strategic bet (that's the [Chief AI Officer](/ai-accountability/chief-ai-officer/index.md)'s).

## Why the role is still finding its home

This isn't a new-title problem you can fix by hiring a "Head of AI Governance" and calling it done. A 2024 IAPP survey found the work is currently split across privacy teams (22%), legal and compliance (22%), IT (17%), data governance (10%), ethics and compliance (6%), and security (5%) — with half of AI governance professionals sitting inside ethics, compliance, privacy, or legal functions rather than a dedicated AI governance seat ([IAPP, 2024](#ev-iapp-ai-governance-2024-reporting-line-split)).

That split isn't necessarily wrong. Privacy teams already run impact-assessment processes that map cleanly onto AI risk review. Legal and compliance already track regulatory change. What matters is that *someone* owns the operationalization end to end, wherever they sit — not that the title says "AI governance" on the door.

## Where it sits, and who it isn't

- **[AI Risk Officer](/ai-accountability/ai-risk-officer/index.md)** owns whether a model is *accurate* — validation, drift, technical soundness. You own whether using it is *allowed* — policy conformance, fairness, ethical-use sign-off. A model can pass their review and fail yours, and vice versa.
- **[Chief AI Officer](/ai-accountability/chief-ai-officer/index.md)** owns the strategic bet and the budget. You set the guardrails the bet has to operate inside — you don't decide whether to make the bet.
- Common home bases for this seat: privacy, legal/compliance, or a dedicated risk function reporting into one of those. Wherever it sits, the same "three lines of defense" logic applies: this function is the second line, setting policy and providing challenge independent from the teams actually building and shipping AI (the first line).

See [The Accountability Map](/ai-accountability/the-accountability-map.md) for how this seat relates to the others.

## How this playbook is organized

- [The NIST AI RMF in Practice](/ai-accountability/ai-governance-lead/the-nist-ai-rmf-in-practice.md) — Govern, Map, Measure, Manage: what each function concretely requires, not just what it's called.
- [Running the Review Function](/ai-accountability/ai-governance-lead/running-the-review-function.md) — sensitive-use triage, pre-deployment sign-off, and the ISO 42001 management-system shape, via a worked example.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **IAPP — *AI Governance Profession Report*, 2024.** 50% of AI governance professionals are typically assigned to ethics, compliance, privacy or legal teams. [Breakdown:] Privacy 22%, Legal and compliance 22%, IT 17%, Data governance 10%, Ethics and compliance 6%, Security 5%. [View source](https://iapp.org/resources/article/ai-governance-profession-report){#ev-iapp-ai-governance-2024-reporting-line-split} · verified 2026-07-02 · primary
