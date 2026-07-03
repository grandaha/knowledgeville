# Data Readiness

Data readiness is not a bar an organization clears once before doing any AI work. It is a
property of the specific data path a use case touches, and the level a team needs rises
with how autonomous that use case is. Start with [Data Readiness Is a Use-Case
Property](/enterprise-ai-transformation/tracks/03-data-readiness/readiness-is-a-use-case-property.md):
it places any use case on that diagnostic in minutes and tells you which of the pages
below, if any, apply to it.

For the use cases that do need it — those that read or write against a system of record —
data readiness is the most common reason AI programs stall after initial pilots. A model
that performs well in a controlled experiment often degrades sharply in production, not
because the model is wrong, but because the data feeding it is inconsistent, inaccessible,
undocumented, or structured for the system that produced it rather than the system that
needs to consume it. Agentic AI raises the bar further: an agent that reads a customer's
account and acts on it needs the organization to have answered questions about data
ownership, access control, and audit logging that a purely generative, human-reviewed use
case never touches.

This track covers the six components that determine whether a given path is ready. The
[core framework](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/index.md)
leads with [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md)
(dimensions, tooling, and what changes if you train your own models) and [Lineage &
Metadata](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata.md)
(the evidence layer that proves the rest, and the layer that matters most once a use case
acts without review), then covers [Data
Governance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/03-data-governance.md)
(ownership, policy, bias controls), [Access &
Integration](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/04-access-and-integration.md)
(silo patterns, integration architectures), [Infrastructure
Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/05-infrastructure-readiness.md)
(MLOps, LLMOps, AgentOps maturity), and [Security &
Compliance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/06-security-and-compliance.md)
(threat categories, privacy landscape). Seven practitioner guides cover the operational
execution: synthetic data generation, data contracts, data mesh governance, data audits and
automated quality governance, historical data debt remediation, master data management, and
data labeling programs.

The assessment section provides two tools — an [AI Readiness Assessment
Framework](/enterprise-ai-transformation/tracks/03-data-readiness/04-assessment-and-measurement/ai-readiness-assessment-framework.md)
that checks a single use case first and only reaches for its optional seven-dimension
portfolio lens when a team is planning several through-the-record initiatives at once, and
a [Total Cost of Data
Debt](/enterprise-ai-transformation/tracks/03-data-readiness/04-assessment-and-measurement/total-cost-of-data-debt.md)
model for quantifying the business case for remediation investment where remediation is
actually warranted.

Leaders looking for the decision-level picture before going deeper should start with the
[executive
summary](/enterprise-ai-transformation/tracks/03-data-readiness/01-executive-summary.md),
which distills the core argument and the sequence of investments the use cases that need
it should make to move from data-constrained to data-ready.

## In this section

| Page | Last updated |
| --- | --- |
| [Data Readiness Is a Use-Case Property](readiness-is-a-use-case-property.md)<br>Data readiness is a property of the path a use case touches, not an estate-wide gate. How to place a use case on that path. | Updated 2026-07-03 |
| [Executive Summary](01-executive-summary.md)<br>A one-page synthesis of the AI Data Readiness knowledge base — for leaders deciding where to invest before funding AI. | Updated 2026-07-03 |
| [Data Readiness Framework](02-framework/)<br>The six foundational components of AI data readiness, each covering the full framework, AI-specific failure modes, tooling landscape, and a practical readiness checklist. | Updated 2026-07-03 |
| [Practitioner Guides](03-practitioner-guides/)<br>Operational how-to guides for each AI data readiness discipline — methodology, tooling, and step-by-step implementation. | Updated 2026-06-16 |
| [Assessment & Measurement](04-assessment-and-measurement/)<br>Tools for determining where your organization stands across all six readiness dimensions and making the business case for investment. | Updated 2026-06-16 |
| [Strategy & Organization](05-strategy-and-organization/)<br>The human and organizational layer of data readiness — building the conditions for technical programs to actually stick. | Updated 2026-06-16 |
