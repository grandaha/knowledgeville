---
type: Playbook
title: Synthetic Data Generation
description: A practitioner guide to generating synthetic data that statistically mirrors real data — when to use it, how it is generated, and the non-negotiable role of fidelity validation.
tags: [synthetic-data, data-privacy, mlops, data-generation, fidelity-validation]
timestamp: "2026-06-12"
---

## What Synthetic Data Actually Is

Synthetic data is artificially generated data that statistically mirrors real data — same distributions, same correlations, same patterns — without containing any actual records about real people or real business events.

The practical value is straightforward: organizations that can't use real data for AI training — because it contains PII, PHI, or proprietary information — can use synthetic data instead. The model trains on statistically equivalent data without the privacy, compliance, or competitive exposure of using real records.

But synthetic data is not a universal solution or a free pass. It solves specific problems. Used outside those problems, it introduces risks that are often harder to detect than the original issue.

> Gartner predicted **75%** of businesses would use generative AI to create synthetic customer data by 2026, up from less than 5% in 2023 ([Gartner, 2024](#ev-gartner-genai-for-business-2024-synthetic-customer-data))

> By 2030, **synthetic data will overshadow real data** in AI models, Gartner predicts ([Gartner, 2021](#ev-gartner-maverick-2021-synthetic-overshadow))

> **76%** of organizations experienced a sensitive-data incident in non-production environments over the past three years — the environment where synthetic data would have been the safe alternative ([K2view, 2026](#ev-k2view-2026-state-enterprise-data-compliance-nonprod-incidents))

> Models trained on low-fidelity synthetic data can perform well in evaluation and **fail silently in production** — because the synthetic data passed all the obvious checks while missing the patterns that mattered

---

## When to Use It (and When Not To)

Synthetic data solves three specific problems:

**Privacy constraint** — real data contains PII or PHI that cannot legally be used for training without GDPR, CCPA, or HIPAA exposure. Synthetic data lets you train without touching real records.

**Data scarcity** — a rare event (fraud, equipment failure, a rare medical condition) doesn't appear frequently enough in real data to train a reliable model. Synthetic generation can produce more examples of the rare class.

**Safe environments** — development, testing, and staging environments that need realistic data without the compliance risk of copying production data.

Do not use synthetic data when:

- Real, consented, properly governed data is available. Real data is always the better option.
- The use case requires actual historical events — audit trails, legal records, compliance reporting.
- You can't validate that the generation process preserved the statistical patterns that matter for your model.

---

## How Synthetic Data Is Generated

There is no single right generation method. The choice depends on three things: the data type (tabular, text, image, time-series), the complexity of relationships between fields, and the fidelity requirements of the downstream model. Here is how the main methods compare and when each is appropriate.

### Statistical methods

**Gaussian Copula** models the statistical correlations between fields and samples from that distribution. The right starting point for tabular data where preserving relationships between columns is the primary requirement — it's fast, computationally light, and well understood. The limitation is its core assumption: that relationships between fields follow a Gaussian distribution. When real data has complex non-linear dependencies, Gaussian Copula will miss them.

**CTGAN (Conditional Tabular GAN)** uses a generative adversarial network specifically designed for tabular data. A generator produces synthetic records; a discriminator tries to distinguish them from real ones; they compete until the discriminator can't reliably tell the difference. Better than statistical methods at capturing complex, non-linear patterns. Computationally heavier and requires more training data to converge well. The right choice when Gaussian Copula produces synthetic data with the right column statistics but wrong inter-column relationships.

**Variational Autoencoders (VAE)** encode data into a compressed latent representation and decode it back, learning the underlying distribution in the process. Used for both tabular and image data. A middle ground between Gaussian Copula and CTGAN in terms of complexity and fidelity.

### LLM-based methods

Large language models can generate synthetic text, synthetic structured records from schema descriptions, and synthetic conversations for fine-tuning. NVIDIA's NeMo Data Designer (formerly Gretel, acquired March 2025) supports dependency-aware generation from seed data with built-in validation including LLM-as-a-judge scoring. Particularly valuable for generating diverse training examples for NLP models and customer service AI — use cases where statistical methods can't capture the semantic variety of real language.

### Rule-based methods

Generates data from explicit business rules and defined distributions. Fully controllable and auditable — every record is traceable to the rules that produced it. The right choice when the rules governing valid data are well understood and the primary requirement is correctness rather than statistical fidelity. The limitation: rule-based generation will miss emergent patterns in real data that weren't explicitly captured in rules.

---

## The Non-Negotiable: Fidelity Validation

This is the step most teams skip. It is also the step that determines whether your synthetic data program produces useful models or expensive failures.

Synthetic data that doesn't faithfully reproduce the statistical properties of real data produces models that fail in production. The model trains successfully, evaluation metrics look fine, and then production performance degrades — in a way that's very hard to diagnose because the training data passed all the obvious checks.

**What fidelity validation must confirm** — before any synthetic dataset is used for model training:

- Column-level distributions match — means, standard deviations, and percentiles for numeric fields; value frequencies for categorical fields
- Correlations between fields are preserved — if high transaction amounts correlate with fraud in real data, that relationship must exist in the synthetic data a fraud model trains on
- Rare events appear at the right frequency — not inflated, not suppressed
- Temporal patterns preserved for time-series — seasonality, trends, and autocorrelation must survive the generation process
- Business rules hold — order dates cannot precede customer creation dates; shipped orders must have shipping addresses

**How to validate** — four complementary techniques, used together:

**TSTR (Train on Synthetic, Test on Real)** — train a model on synthetic data, evaluate it on a held-out real dataset. If fidelity is high, performance should approach what you'd get training on real data. This is the most direct measure of whether synthetic data is actually fit for its purpose — because it tests the thing that matters, not a proxy for it.

**TRTS (Train on Real, Test on Synthetic)** — the inverse. Confirms the synthetic data reflects the same patterns the real data contains. Used alongside TSTR to catch asymmetric fidelity failures.

**Statistical comparison** — Kolmogorov-Smirnov tests for distribution similarity, Jensen-Shannon divergence for probability distributions, correlation matrix comparison. These are fast, cheap, and should run automatically as part of every generation pipeline.

**Discriminator testing** — train a binary classifier to distinguish real from synthetic records. If the classifier performs well, the synthetic data is detectable — meaning low fidelity. The goal is a classifier that performs at or near chance, because that means the synthetic data is indistinguishable from real.

---

## Privacy: What Synthetic Data Does and Doesn't Guarantee

The most dangerous misconception in the field: that synthetic data is automatically private.

Synthetic data reduces privacy risk. It does not eliminate it.

**What it protects against:** a synthetic record is not a real person's record. An attacker who obtains a synthetic dataset cannot look up a synthetic email address and find the corresponding individual.

**What it does not protect against:**

- **Membership inference** — in some cases, an attacker can determine whether a specific real person's record was used to train the synthetic generator, even without seeing any synthetic record that resembles them.
- **Re-identification via rare combinations** — if the real dataset contains a very rare combination of attributes, and the generator learned that pattern, a synthetic record with those attributes may effectively identify the real person.
- **Distribution leakage** — the statistical properties of the real dataset are intentionally preserved in the synthetic data. An attacker with background knowledge can infer information about the real population.

The legal position: synthetic data derived from personal data may still be classified as personal data under GDPR if re-identification is reasonably possible. Legal review is required before using synthetic data to satisfy privacy obligations. Do not assume compliance.

**Differential privacy** adds mathematical privacy guarantees by limiting how much any single real record can influence the generated distribution. Tradeoff: reduced fidelity, particularly for rare events and edge cases. Worth it for high-sensitivity use cases; potentially damaging for rare-event classification models.

---

## Tooling

**NVIDIA NeMo Data Designer (formerly Gretel)** — open-sourced under Apache 2.0 following NVIDIA's acquisition of Gretel in March 2025. A Python framework for generating synthetic data from scratch or from seed data using statistical samplers and LLMs. Dependency-aware generation with built-in validation including LLM-as-a-judge scoring. Developer-focused — configured in code, not a GUI. Best leverage in the NVIDIA/NeMo ecosystem for teams building generation into training pipelines programmatically.
Website: [https://github.com/NVIDIA/NeMo](https://github.com/NVIDIA/NeMo) \| Open source (Apache 2.0).

**MOSTLY AI** — enterprise platform specializing in tabular and time-series synthetic data. Strong privacy guarantees with differential privacy options. SOC 2 certified. Focused specifically on financial services, healthcare, and telecom.
Website: [https://mostly.ai](https://mostly.ai) \| Contact for quote.

**K2view** — Gartner Visionary for the third consecutive year in 2025. Generates synthetic data at the entity level — customer, order, product — while preserving referential integrity across related tables. Critical for complex enterprise schemas where a synthetic customer record must have consistent synthetic orders, addresses, and interactions.
Website: [https://www.k2view.com](https://www.k2view.com) \| Contact for quote.

[**Tonic.ai**](http://Tonic.ai)** (Tonic Fabricate)** — developer-focused platform that generates realistic data from real schemas quickly. Particularly strong for creating test databases that mirror production structure without production data.
Website: [https://www.tonic.ai](https://www.tonic.ai) \| Contact for quote.

**YData** — Python-first platform built around ydata-profiling (formerly pandas-profiling). Focuses on tabular data with strength in time-series and imbalanced datasets. Open source core.
Website: [https://ydata.ai](https://ydata.ai) \| Open source core; paid cloud tier available.

**Synthea** — open-source synthetic patient generator that produces realistic electronic health records for entire synthetic populations. The standard tool for healthcare AI teams who need clinical training data without HIPAA exposure.
Website: [https://synthetichealth.github.io/synthea](https://synthetichealth.github.io/synthea) \| Fully open source.

---

## Readiness Checklist

- [ ] Use case confirmed as appropriate for synthetic data — privacy constraint, data scarcity, or safe environment need
- [ ] Generation method selected based on data type and relationship complexity
- [ ] Fidelity validation plan defined before generation begins — not after
- [ ] TSTR and TRTS testing included in the validation protocol
- [ ] Statistical comparison tests specified — distribution similarity, correlation matrix, value frequencies
- [ ] Edge case coverage validated — rare events at correct frequency
- [ ] Business rule validation included — synthetic records satisfy all domain constraints
- [ ] Legal review completed — synthetic data classified correctly under applicable privacy law
- [ ] Differential privacy considered for high-sensitivity use cases
- [ ] Synthetic data versioned and tracked with lineage, provenance, and generation parameters
- [ ] Model trained on synthetic data evaluated against real held-out data before production deployment

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Gartner — *What Generative AI Means for Business*, 2024.** By 2026, 75% of businesses will use generative AI to create synthetic customer data, up from less than 5% in 2023. [View source](https://www.gartner.com/en/insights/generative-ai-for-business){#ev-gartner-genai-for-business-2024-synthetic-customer-data} · verified 2026-06-21 · ⚠ secondary mirror
- **Gartner — *Maverick Research: Forget About Your Real Data - Synthetic Data Is the Future of AI (Ramos & Subramanyam)*, 2021.** By 2030, synthetic data will overshadow real data in AI models. [View source](https://www.gartner.com/en/documents/4002912){#ev-gartner-maverick-2021-synthetic-overshadow} · verified 2026-06-21 · ⚠ secondary mirror
- **K2view — *2026 State of Enterprise Data Compliance Survey*, 2026.** 76% of organizations experienced a sensitive-data incident in non-production environments over the past three years. [View source](https://www.k2view.com/news-blog/2026-state-of-enterprise-data-compliance-survey/){#ev-k2view-2026-state-enterprise-data-compliance-nonprod-incidents} · verified 2026-06-21 · ⚠ secondary mirror
