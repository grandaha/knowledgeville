# Update Log

## 2026-08-24
* **Update**: [Access & Integration](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/04-access-and-integration.md)
  now attributes its data-architecture direction to Deloitte's State of AI in the Enterprise
  2026 — a survey of 3,235 leaders across 24 countries — and cites it. The passage previously
  paraphrased that report almost verbatim under the heading "the 2026 consensus", with no
  citation. A second passage on that page, and one in
  [Data Mesh Governance in Practice](/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/data-mesh-governance-in-practice.md),
  also claimed a "2026 consensus" — one sourced to "multiple implementation reports" and one
  to nobody. Both now read as what they are: this framework's recommendation.
* **Update**: [AI Governance & Risk: Executive Summary](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/01-executive-summary.md)
  drops the claim that most enterprises run governance "three to four years behind" their AI
  deployments. Nothing supported the figure. The point it was making — that governance is
  routinely stood up after the AI it governs — survives without the invented precision.
* **Update**: [AI Governance Framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md)
  no longer opens on an unsourced claim about what share of enterprise AI is assembled from
  third-party components. The concrete list that follows — foundation models via API, AI-enabled
  SaaS, hyperscaler infrastructure — makes the case without needing a measured proportion.

## 2026-08-24
* **Update**: [Lineage & Metadata](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata.md),
  [Data Governance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/03-data-governance.md),
  [Infrastructure Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/05-infrastructure-readiness.md)
  and [Security & Compliance](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/06-security-and-compliance.md)
  drop a trailing "New Glossary Terms from This Component" block. It listed terms in bold,
  told the reader to see the glossary, and linked nothing — and the glossary defined none of
  the terms it named. Each page already defines these terms in context, which is where they
  belong.
* **Update**: [Glossary](/enterprise-ai-transformation/glossary.md) section introductions no
  longer refer to "Component 02", "Component 03" and so on. That numbering came from an
  earlier structure and no longer matched any page. Each introduction now links to the page
  its terms belong to.
* **Update**: [Lineage & Metadata](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata.md)
  cuts two passages that asserted what "most enterprises" had realised and what enterprises
  reporting AI value had done, neither of which was sourced. The AI context layer section now
  explains what makes it a layer rather than a catalog: an agent queries it mid-task, so it
  cannot afford the staleness a catalog can. The tooling table also drops an analyst award
  from one vendor's suitability note — that column describes fit, and the award was carried
  for one vendor when others in the same table hold it too.

## 2026-08-23
* **Update**: [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md)
  corrects a misattribution. The six quality dimensions were credited to DAMA-DMBOK; they
  come from a DAMA UK working group paper of October 2013, and DAMA-DMBOK is a broader,
  separate publication. The page now says so, and notes that no single canonical list exists —
  DAMA's Dutch chapter distilled 60 preferred dimension definitions from 127 across nine
  authoritative sources.
* **Update**: [Data Audits & Automated Quality Governance](/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/data-audits-and-automated-quality-governance.md)
  extends the audit walkthrough from two dimensions to all six. New steps cover auditing for
  consistency, timeliness, validity, and uniqueness — each with its audit techniques, a scoring
  formula, and a threshold. A new step covers the composite score: how to choose dimension
  weights from the use case's failure mode, the composite formula, a worked example, and one
  threshold table for all six dimensions plus the composite.
* **Update**: The same guide now states plainly that its thresholds are recommended starting
  points rather than standards. ISO 8000-8:2015 requires a threshold to be set per business
  and per measured object, and says explicitly that it does not set one. Readers are told to
  set their own against the consequence of failure, and to record the reasoning.
* **Update**: [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md)
  now links its scoring section to the audit guide that supplies the formulas, which it
  previously did not. Its blanket "below 70 on any dimension" rule is replaced — that number
  contradicted the per-dimension thresholds in the audit guide. The worked example now shows
  that a dataset can score 84.0 overall and still fail three blocking gates.

## 2026-07-08
* **Creation**: [MCP and the Context Gap](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/06-mcp-and-the-context-gap.md)
  explains what the Model Context Protocol actually standardizes (six primitives over JSON-RPC),
  the gap its own specification admits it leaves open (memory, semantic agreement, access
  enforcement), and why every "context layer" vendor pitch is really a bet on filling that
  acknowledged gap differently.
* **Update**: [Tooling Landscape](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/03-tooling-landscape.md)
  adds a new "Memory and Context Frameworks" category (Mem0, Cognee, Zep, Graphiti, Redis Iris),
  and [Technology Architecture Framework](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md)
  cross-links to the new MCP page.

## 2026-07-06
* **Update**: [Practitioner Guide: Running a Workflow Optimization Program](/enterprise-ai-transformation/tracks/05-workflow-optimization-and-automation/05-practitioner-guide-running-a-workflow-optimization-program.md)
  adds a section naming DAIN Studios' and ServiceNow's competing "A.G.E.N.T." frameworks, mapping
  both onto this guide's own four phases (they're a relabeling, not an addition), and naming the
  real gaps neither closes — multi-step agent evaluation, non-determinism versus irreversible-action
  safety, error compounding across steps, and context/tool-selection limits. Also notes DAIN's
  framework is the methodology behind Harvard Data Science Initiative's "Agentic AI Intensive" course,
  co-taught by DAIN's own co-founders alongside independent faculty.

## 2026-07-03
* **Creation**: [Data Readiness Is a Use-Case Property](/enterprise-ai-transformation/tracks/03-data-readiness/readiness-is-a-use-case-property.md)
  opens the whole track with a diagnostic: whether a use case's data routes around or
  through the system of record. Leads the track ahead of the Executive Summary.
* **Update**: [Data Quality](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality.md)
  is retitled and re-scoped: quality requirements now follow the path a use case touches,
  and the material specific to training or fine-tuning your own model (label noise,
  representation bias, drift, poisoning) is clearly scoped as optional reading rather than
  presented as a universal AI truth.
* **Update**: [AI Readiness Assessment Framework](/enterprise-ai-transformation/tracks/03-data-readiness/04-assessment-and-measurement/ai-readiness-assessment-framework.md)
  now runs in two layers: a fast use-case-first check (place the use case's data path and
  autonomy level, decide whether the heavier assessment is even needed) ahead of the
  seven-dimension organizational scoring, which is demoted to an optional portfolio lens
  for teams planning several initiatives at once. The interpretation bands no longer read
  as a blanket "fix everything before any AI" gate.
* **Update**: [Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md)
  overview and [Executive Summary](/enterprise-ai-transformation/tracks/03-data-readiness/01-executive-summary.md)
  now lead with the use-case diagnostic instead of an estate-wide framing, and the
  [Data Readiness Framework](/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/index.md)
  reorders to put Lineage & Metadata second — the evidence layer that matters most once a
  use case acts without review — ahead of Governance and Access & Integration, both of
  which now cross-link the use-case diagnostic as well.
* **Update**: [Data Labeling & Annotation Programs](/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/data-labeling-and-annotation-programs.md)
  and [Data Mesh Governance in Practice](/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/data-mesh-governance-in-practice.md)
  now open with a scope note: labeling applies only if you train or fine-tune your own
  models, and data mesh is an organization-scale option, not a per-use-case readiness step.
  [Master Data Management](/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/master-data-management.md)
  is reframed from "run an MDM program" to "resolve the entities a single use case needs,"
  with the full program covered as what's warranted at organizational scale.
* **Update**: [Program Architecture](/enterprise-ai-transformation/running-the-program/program-architecture.md)
  now cross-links its CDAO, AI Program Lead, and Track Owner roles to their matching
  operator's manuals in AI Accountability, and names the typical owner (with cited
  evidence) for the five tracks — data readiness, platform, workflow, talent, and
  measurement — that don't have a dedicated AI Accountability role.
* **Audit**: [Program Architecture — Accountability Cross-Links, July 2026](/enterprise-ai-transformation/validation/audits/2026-07-03-program-architecture-accountability-links.md)
  — corrected a source misattribution in the new citations above before merge.

## 2026-06-29
* **Update**: Began tracking this bundle's change history here, as a per-bundle OKF log that ships with the bundle.
