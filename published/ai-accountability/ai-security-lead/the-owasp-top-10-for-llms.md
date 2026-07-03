---
type: Reference
title: The OWASP Top 10 for LLM Applications
description: The ten vulnerability categories that define what this role tests for.
tags: [ai-security-lead, owasp]
timestamp: "2026-07-02"
---

OWASP's Top 10 for LLM Applications is the closest thing this field has to a shared vocabulary — a ranked list of the vulnerability categories that show up again and again in real LLM-based systems ([OWASP, 2025](#ev-owasp-llm-top-10-2025-list)). Use it as a checklist for what a review needs to cover, not a compliance box to tick once.

## The list

1. **Prompt Injection** — user input alters the model's behavior in ways the system designer didn't intend, overriding instructions or extracting data it shouldn't share.
2. **Sensitive Information Disclosure** — the model exposes private, proprietary, or otherwise sensitive information through its outputs.
3. **Supply Chain** — vulnerabilities inherited from third-party models, training data, fine-tuning services, or plugins the system depends on.
4. **Data and Model Poisoning** — pre-training, fine-tuning, or embedding data is manipulated to introduce vulnerabilities, backdoors, or bias.
5. **Improper Output Handling** — insufficient validation or sanitization of what the model produces before it's used downstream (rendered in a browser, executed as code, passed to another system).
6. **Excessive Agency** — an agentic system is granted more autonomy, permissions, or tool access than its actual task requires.
7. **System Prompt Leakage** — the instructions meant to stay hidden from the user get exposed, handing an attacker the system's own playbook.
8. **Vector and Embedding Weaknesses** — security gaps specific to retrieval-augmented systems, where the vector store or embedding pipeline becomes the attack surface.
9. **Misinformation** — the model generates false or misleading content that's presented with unwarranted confidence.
10. **Unbounded Consumption** — the system allows unrestricted resource use, covering denial-of-service, cost exploitation, and unauthorized model replication.

## What's changed from earlier versions

This list evolves as real-world incidents surface new patterns. One thing worth knowing if you've used an older version of this list: model theft is now folded into **Unbounded Consumption** rather than standing alone — OWASP's own description explicitly covers stealing IP by cloning a model's behavior through API extraction ([OWASP, 2025](#ev-owasp-llm10-2025-model-theft-scope)). Treat this as a living list — check for the current version before you scope a review, not this page's snapshot of it.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **OWASP (GenAI Security Project) — *OWASP Top 10 for LLM Applications*, 2025.** LLM01:2025 Prompt Injection; LLM02:2025 Sensitive Information Disclosure; LLM03:2025 Supply Chain; LLM04:2025 Data and Model Poisoning; LLM05:2025 Improper Output Handling; LLM06:2025 Excessive Agency; LLM07:2025 System Prompt Leakage; LLM08:2025 Vector and Embedding Weaknesses; LLM09:2025 Misinformation; LLM10:2025 Unbounded Consumption. [View source](https://genai.owasp.org/llm-top-10/){#ev-owasp-llm-top-10-2025-list} · verified 2026-07-02 · primary
- **OWASP (GenAI Security Project) — *LLM10:2025 Unbounded Consumption*, 2025.** Attacks designed to disrupt service, deplete the target's financial resources, or even steal intellectual property by cloning a model's behavior all depend on a common class of security vulnerability... Model Extraction via API: Attackers may query the model API using carefully crafted inputs and prompt injection techniques to collect sufficient outputs to replicate a partial model or create a shadow model. [View source](https://genai.owasp.org/llmrisk/llm102025-unbounded-consumption/){#ev-owasp-llm10-2025-model-theft-scope} · verified 2026-07-02 · primary
