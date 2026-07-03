# Data Readiness Framework

[Data readiness is a use-case property](/enterprise-ai-transformation/tracks/03-data-readiness/readiness-is-a-use-case-property.md):
each component below matters in proportion to whether your use case routes through the
system of record, and how much autonomy it runs at. AI data readiness is not a single
problem — it is six problems that depend on each other. You can have pristine data quality
but still fail AI at scale if governance is absent and no one owns the rules. You can have
excellent governance but block every AI use case if access and integration patterns have
not caught up to what models actually need. Lineage and metadata make quality and
governance provable rather than asserted — and provability is the requirement that rises
fastest as a use case moves toward autonomous action, since there is no longer a human in
the loop to catch what the data got wrong. Infrastructure determines whether any of it
holds in production. Security wraps the entire stack and is the one layer where a gap does
not just slow AI down — it creates liability.

The six components form a dependency chain, not a checklist. Weakness in an early layer
caps what later layers can do. An AI system trained on untracked data has a lineage problem
regardless of how good its infrastructure is. A governance policy that covers no agentic
workloads is already out of date. The right remediation sequence — identify the binding
constraint, fix it, then reassess — requires understanding how the layers interact.

Each subpage below covers the full conceptual framework for its component, the AI-specific
failure modes that traditional data programs miss, the current tooling landscape with
specific recommendations, and a practical readiness checklist you can use in an assessment
session.

Read in this order if you are new to the topic — lineage comes second because it is the
evidence layer that proves the others are working, and the layer whose absence hurts most
once a use case starts acting without review. Jump to a specific component if you are
targeting a known gap.

| Component | What it covers |
| --- | --- |
| [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md) | Six quality dimensions, weighted scoring, tooling, checklist, and what changes if you train your own models |
| [Lineage & Metadata](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata.md) | Four lineage types, active metadata, business glossary for AI, model lineage — the evidence layer that makes everything else provable |
| [Data Governance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/03-data-governance.md) | Ownership structures, bias monitoring, explainability, NIST / EU AI Act / ISO 42001 crosswalk |
| [Access & Integration](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/04-access-and-integration.md) | Four integration patterns, lakehouse / fabric / mesh architectures, agentic access requirements |
| [Infrastructure Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/05-infrastructure-readiness.md) | MLOps, LLMOps, AgentOps, seven infrastructure layers, six-level maturity ladder |
| [Security & Compliance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/06-security-and-compliance.md) | Six AI threat categories, global privacy law, access control architecture, audit trails |

## In this section

| Page | Last updated |
| --- | --- |
| [Data Quality](01-data-quality.md)<br>What data quality means for the path a use case touches — six dimensions, a five-step framework, tooling, and what changes if you train models. | Updated 2026-07-03 |
| [Lineage & Metadata](02-lineage-and-metadata.md)<br>The evidence layer that makes data quality, governance, and access provable — four lineage types, column-level lineage, active metadata, the business glossary, model lineage, and the AI context layer. | Updated 2026-07-03 |
| [Data Governance](03-data-governance.md)<br>Why governance is different for AI — ownership, policy infrastructure, bias monitoring, explainability, the NIST / EU AI Act / ISO 42001 landscape, agentic governance, and a readiness checklist. | Updated 2026-07-03 |
| [Access & Integration](04-access-and-integration.md)<br>The bridge between data that exists and data AI can use — the silo problem, four integration patterns, lake/warehouse/lakehouse/fabric/mesh architectures, cataloging, and agentic access requirements. | Updated 2026-07-03 |
| [Infrastructure Readiness](05-infrastructure-readiness.md)<br>The most-skipped step in enterprise AI — the MLOps/LLMOps/AgentOps stack, the seven infrastructure layers, a maturity ladder, tooling landscape, and a readiness checklist. | Updated 2026-06-12 |
| [Security & Compliance](06-security-and-compliance.md)<br>Security and compliance as a first-order AI problem — how AI changes the threat model, six AI security threat categories, the privacy compliance landscape, access control, audit trails, and privacy-preserving techniques. | Updated 2026-06-12 |
