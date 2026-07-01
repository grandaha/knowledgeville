---
type: Audit
title: "Citation audit — Open Knowledge Format bundle (2026-07-01)"
description: "First citation audit of the seven-page OKF bundle against the canonical OKF specification."
tags: [validation, audit]
timestamp: "2026-07-01"
appendix: true
---

**Scope:** the architecture page and all six leaf pages of the Open Knowledge Format bundle.
**Verified against:** the canonical OKF specification, v0.1.
**Posture:** `selective` / `verify-embedded-facts` — the claims are mostly conceptual, with essentially no statistics.

## Result

**0 confirmed-wrong, 0 could-not-verify** across all seven pages.

Every claim cited to the specification is faithful to it: the definition, the "read a file, read OKF" accessibility, `type` as the only required field, unknown-field tolerance, the concept-ID rule, prose-borne links, the `# Citations` provenance convention, the three non-goals, and the versioning plan. The rich verification layer (evidence ledger, per-claim checking, build gates) is correctly presented as a Knowledgeville extension, not as core OKF v0.1. The MCP claim was confirmed against the live endpoint.

## Notes

- The comparison to knowledge graphs, schema.org, and RAG is the bundle's own analytical framing; the specification does not name those formats. The pages present it as our framing, and the sourced citation attaches only to the spec's stated non-goals. Correct under this bundle's posture.
