# Update Log

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
