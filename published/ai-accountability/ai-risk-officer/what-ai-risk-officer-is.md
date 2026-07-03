---
type: Concept
title: What the AI Risk Officer Is — and the Role
description: "What model risk means, why the function is rooted in banking, and what it deliberately doesn't cover yet."
tags: [ai-risk-officer, role-definition]
timestamp: "2026-07-02"
lead: true
---

Model risk management is not a new discipline invented for AI. Banks have run it for over a decade under federal guidance, because a model that's wrong — not hacked, not misused, just wrong — can lose as much money as a bad trade. The AI Risk Officer is that function, pointed at AI/ML models.

## What model risk actually means

Not every piece of software is a "model" in this sense. The regulatory definition is specific: a complex quantitative method, system, or approach that applies statistical, economic, or financial theories to process input data into quantitative estimates. Simple arithmetic, spreadsheets, and deterministic rule-based processes are explicitly excluded — this function is about systems that produce an estimate, not systems that just execute a formula.

The job is accuracy, not ethics. You own whether a model's outputs are right, stay right over time, and were built and reviewed the way a serious estimate deserves to be. You do not own whether the model's *use* is fair, legal, or aligned with company policy — that's a different job (see below).

## Where this comes from, and what it deliberately doesn't cover

This function is rooted in bank supervisory guidance — most recently the OCC, Federal Reserve, and FDIC's revised Model Risk Management guidance, Bulletin 2026-13 (April 2026), which supersedes the prior 2011 guidance known as SR 11-7. It's guidance, not an enforceable rule, and it's aimed primarily at large banks — regulators say it's "expected to be most relevant to banking organizations with over $30 billion in total assets" ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-scope)). Its principles have become the de facto standard for model risk functions well beyond banking, in insurance, fintech, and elsewhere.

Here's the detail worth knowing before you assume too much: the current guidance explicitly does **not** yet cover generative or agentic AI. Regulators were direct about it — "Generative AI and agentic AI models are novel and rapidly evolving. As such, they are not within the scope of this guidance" ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-genai-exclusion)) — with a request for information on how to extend the framework to those systems still pending. If your organization is validating an LLM-based system today, you're extending established principles into a gap the regulators themselves haven't yet filled — say so plainly to whoever you report to, rather than implying the ground is more settled than it is.

## Where it sits, and who it isn't

- **AI Governance Lead** owns *policy* — regulatory conformance, fairness review, ethical-use sign-off. You own *math* — is this model accurate, and does it stay that way. A model can pass your review and still fail theirs, and vice versa.
- **Chief Risk Officer** owns enterprise-wide risk across credit, market, operational, and liquidity exposure. Model risk is one input to that bigger picture, not a replacement for it — you feed the CRO's view, you don't own it.
- **[Chief AI Officer](/ai-accountability/chief-ai-officer/what-chief-ai-officer-is.md)** owns the strategic bet. You don't decide whether to build a model; you decide whether the one that got built is trustworthy enough to rely on.

A proposed title for this seat — "Chief AI Risk Officer" — has been floated in industry commentary, but it's advocacy for a role that should exist, not evidence that it does ([ISACA, 2025](#ev-isaca-cairo-2025-proposal)). The function is real and well-established; the title is still unsettled. See [The Accountability Map](/ai-accountability/the-accountability-map.md) for how this seat relates to the others.

## How this playbook is organized

- [Validating and Monitoring Models](/ai-accountability/ai-risk-officer/validating-and-monitoring-models.md) — the three-part discipline that does the actual work: conceptual soundness, outcomes analysis, and ongoing monitoring for drift.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** This guidance does not set forth enforceable standards or prescriptive requirements; accordingly, non-compliance with this guidance will not result in supervisory criticism against a banking organization... expected to be most relevant to banking organizations with over $30 billion in total assets. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-scope} · verified 2026-07-02 · primary
- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** Generative AI and agentic AI models are novel and rapidly evolving. As such, they are not within the scope of this guidance... the principles described in this guidance apply to traditional statistical and quantitative models and non-generative, non-agentic AI models. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-genai-exclusion} · verified 2026-07-02 · primary
- **ISACA (Charles Cresson Wood) — *ISACA Now Blog — The New Role of the Chief Artificial Intelligence Risk Officer*, 2025.** The New Role of the Chief Artificial Intelligence Risk Officer — an advocacy piece analogized to the historical emergence of the CISO and CPO roles, proposing the title rather than documenting its adoption. [View source](https://www.isaca.org/resources/news-and-trends/isaca-now-blog/2025/the-new-role-of-the-chief-artificial-intelligence-risk-officer){#ev-isaca-cairo-2025-proposal} · verified 2026-07-02 · primary
