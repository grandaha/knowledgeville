---
type: Playbook
title: The NIST AI RMF in Practice
description: "Govern, Map, Measure, Manage — what each function concretely requires, not just what it's called."
tags: [ai-governance-lead, nist-ai-rmf]
timestamp: "2026-07-02"
---

The NIST AI Risk Management Framework's four functions sound like a diagram until you have to actually run them. Here's what each one requires in practice, and the order they typically get built in.

## Govern — the culture and structure underneath everything else

Govern cultivates and implements a culture of risk management across everyone who designs, develops, deploys, evaluates, or acquires AI systems ([NIST, 2023](#ev-nist-ai-rmf-2023-govern-function)). Concretely: the processes, documents, and organizational schemes that let you anticipate, identify, and manage AI risk before it becomes an incident. This is the function you build first — Map, Measure, and Manage all assume a governance structure already exists to feed into.

## Map — knowing what you're actually looking at

Map establishes the context to frame an AI system's risk ([NIST, 2023](#ev-nist-ai-rmf-2023-map-function)). Before you can assess whether a system is risky, you have to document its intended purpose, its potentially beneficial uses, the laws and norms specific to its context, and where it will actually be deployed. Skipping this step is how organizations end up assessing a system against the wrong risk profile — reviewing a customer-facing chatbot with the same lens as an internal analytics tool.

## Measure — proving the risk assessment isn't a guess

Measure applies quantitative, qualitative, or mixed methods to analyze, assess, benchmark, and monitor AI risk and its impacts ([NIST, 2023](#ev-nist-ai-rmf-2023-measure-function)). The bar NIST sets is specific: your test, evaluation, verification, and validation processes need to be objective, repeatable, or scalable — with the metrics and methodology documented, not just "we looked at it and it seemed fine."

## Manage — turning the assessment into action

Manage allocates risk-treatment resources to whatever Map and Measure surfaced, on a regular cadence set by your governance structure ([NIST, 2023](#ev-nist-ai-rmf-2023-manage-function)). This is where a documented risk becomes a prioritized fix, a monitoring plan, or an accepted-risk sign-off — not a report that sits in a shared drive. Manage closes the loop back to Govern: what you learn managing this round's risks should change next round's policy.

## Building it in order

Most functions map naturally onto existing work if you look for it — a Map exercise looks a lot like a privacy impact assessment; Measure overlaps with model testing your engineering team may already do. The job of the AI Governance Lead is less "invent four new processes" and more "find where these four functions already half-exist in your organization, and connect them into one accountable loop."

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **NIST — *AI Risk Management Framework (AI RMF 1.0) — Core Functions*, 2023.** cultivates and implements a culture of risk management within organizations designing, developing, deploying, evaluating, or acquiring AI systems... processes, documents, and organizational schemes that anticipate, identify, and manage the risks a system can pose. [View source](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/){#ev-nist-ai-rmf-2023-govern-function} · verified 2026-07-02 · primary
- **NIST — *AI Risk Management Framework (AI RMF 1.0) — Core Functions*, 2023.** establishes the context to frame risks related to an AI system... document intended purposes, potentially beneficial uses, context-specific laws, norms and expectations, and prospective settings in which the AI system will be deployed. [View source](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/){#ev-nist-ai-rmf-2023-map-function} · verified 2026-07-02 · primary
- **NIST — *AI Risk Management Framework (AI RMF 1.0) — Core Functions*, 2023.** employs quantitative, qualitative, or mixed-method tools, techniques, and methodologies to analyze, assess, benchmark, and monitor AI risk and related impacts... objective, repeatable, or scalable test, evaluation, verification, and validation (TEVV) processes including metrics, methods, and methodologies are in place, followed, and documented. [View source](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/){#ev-nist-ai-rmf-2023-measure-function} · verified 2026-07-02 · primary
- **NIST — *AI Risk Management Framework (AI RMF 1.0) — Core Functions*, 2023.** entails allocating risk resources to mapped and measured risks on a regular basis and as defined by the govern function... plans for prioritizing risk and regular monitoring and improvement. [View source](https://airc.nist.gov/airmf-resources/airmf/5-sec-core/){#ev-nist-ai-rmf-2023-manage-function} · verified 2026-07-02 · primary
