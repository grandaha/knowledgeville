---
type: Playbook
title: Validating and Monitoring Models
description: "The three-part discipline: conceptual soundness, outcomes analysis, and ongoing monitoring for drift."
tags: [ai-risk-officer, model-validation]
timestamp: "2026-07-02"
---

Validation isn't a gate you clear once. It's three separate checks, done at different times, each catching a different way a model goes wrong.

## Conceptual soundness — before the model ships

The first check happens before first use: assessing and documenting the model's design, construction, and developmental testing ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-conceptual-soundness)) — the modeling choices, the assumptions, the data selected, and why. This is where you catch a model built on a bad premise before it ever touches a real decision. For models where a full theoretical review doesn't fit — some AI/ML approaches included — interpretability measures or benchmarking can substitute for a classical soundness argument.

## Outcomes analysis — does it match reality

Once a model is live, compare what it predicted against what actually happened. This is outcomes analysis: comparing model outputs to real-world outcomes to assess performance relative to the model's objectives, typically through back-testing or outlier analysis ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-outcomes-analysis)). A model that looked sound on paper can still fail this check — theory and reality are different tests, and you run both.

## Ongoing monitoring — catching drift before it costs you

The world the model was built for keeps changing after you've validated it. Ongoing monitoring evaluates whether a model is still performing as expected given potential changes in products, exposures, activities, clients, data relevance, or market conditions ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-ongoing-monitoring)). When performance deviates meaningfully from what you'd expect, that's your trigger for an overlay, an adjustment, or full redevelopment — not a reason to wait and see if it self-corrects.

## The governance underneath all three

None of this works without **effective challenge** — critical analysis from objective experts who have both the independence to stay objective and the organizational standing to actually force a change ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-effective-challenge)). A validation function that reports to the same people who built the model, or that can be overruled without consequence, isn't providing effective challenge — it's providing cover.

Keep a model inventory and tier models by materiality — a low-exposure internal tool doesn't need the same scrutiny as a model driving customer-facing decisions. And don't let vendor models off the hook: the same validation principles apply even when you don't have access to the vendor's code or methodology, including ongoing monitoring, outcome analysis, and documentation of any customization you've made ([OCC/Fed/FDIC, 2026](#ev-occ-fed-fdic-bulletin-2026-13-vendor-models)). "We bought it from a reputable vendor" is not a validation result.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** assessing and documenting model design (including key modeling choices, assumptions, qualitative judgments, and data selection), construction, and developmental testing. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-conceptual-soundness} · verified 2026-07-02 · primary
- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** compares model outputs to corresponding real-world outcomes to assess model performance relative to model objectives... back-testing or outlier analysis. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-outcomes-analysis} · verified 2026-07-02 · primary
- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** an evaluation of the extent to which a model is performing as expected given potential changes in products, exposures, activities, clients, data relevance, or market conditions. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-ongoing-monitoring} · verified 2026-07-02 · primary
- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** critical analysis conducted by objective experts... independence to maintain objectivity... organizational standing and influence to effect any change. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-effective-challenge} · verified 2026-07-02 · primary
- **OCC, Federal Reserve, and FDIC — *Supervisory Guidance on Model Risk Management, Bulletin 2026-13*, 2026.** the same validation principles apply even without access to vendor code/methodology... requires ongoing monitoring and outcome analysis of vendor models and documentation of any customization. [View source](https://www.occ.gov/news-issuances/bulletins/2026/bulletin-2026-13a.pdf){#ev-occ-fed-fdic-bulletin-2026-13-vendor-models} · verified 2026-07-02 · primary
