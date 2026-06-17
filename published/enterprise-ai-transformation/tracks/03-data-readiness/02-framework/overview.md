---
type: Concept
title: Data Readiness Framework
description: The six foundational components of AI data readiness, each covering the full framework, AI-specific failure modes, tooling landscape, and a practical readiness checklist.
tags: [data-readiness, framework, ai-data, six-components]
timestamp: "2026-06-16"
---

AI data readiness is not a single problem — it is six problems that depend on each other. You can have pristine data quality but still fail AI at scale if governance is absent and no one owns the rules. You can have excellent governance but block every AI use case if access and integration patterns haven't caught up to what models actually need. Lineage and metadata make quality and governance provable rather than asserted. Infrastructure determines whether any of it holds in production. Security wraps the entire stack and is the one layer where a gap doesn't just slow AI down — it creates liability.

The six components form a dependency chain, not a checklist. Weakness in an early layer caps what later layers can do. An AI system trained on untracked data has a lineage problem regardless of how good its infrastructure is. A governance policy that covers no agentic workloads is already out of date. The right remediation sequence — identify the binding constraint, fix it, then reassess — requires understanding how the layers interact.

Each subpage below covers the full conceptual framework for its component, the AI-specific failure modes that traditional data programs miss, the current tooling landscape with specific recommendations, and a practical readiness checklist you can use in an assessment session.

Read in order if you are new to the topic. Jump to a specific component if you are targeting a known gap.

| # | Component | What it covers |
| --- | --- | --- |
| 01 | [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md) | Six quality dimensions, four AI failure modes, weighted scoring, tooling, checklist |
| 02 | [Data Governance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-data-governance.md) | Ownership structures, bias monitoring, explainability, NIST / EU AI Act / ISO 42001 crosswalk |
| 03 | [Access & Integration](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/03-access-and-integration.md) | Four integration patterns, lakehouse / fabric / mesh architectures, agentic access requirements |
| 04 | [Lineage & Metadata](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/04-lineage-and-metadata.md) | Four lineage types, active metadata, business glossary for AI, model lineage |
| 05 | [Infrastructure Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/05-infrastructure-readiness.md) | MLOps, LLMOps, AgentOps, seven infrastructure layers, six-level maturity ladder |
| 06 | [Security & Compliance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/06-security-and-compliance.md) | Six AI threat categories, global privacy law, access control architecture, audit trails |
