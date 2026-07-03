---
type: Audit
title: Program Architecture — Accountability Cross-Links, July 2026
description: Validation sweep of the new track-ownership citations added to Program Architecture's Roles section.
tags: [audit, citations, validation, program-architecture]
timestamp: "2026-07-03"
---

## Purpose

This document records the results of a citation audit on the new paragraph added to
[Program Architecture](/enterprise-ai-transformation/running-the-program/program-architecture.md)'s
"Roles: From the CDAO to the Working Teams" section, which names the typical owner of the
five tracks (Data Readiness, Technology Architecture & Platform, Workflow Optimization &
Automation, Talent & Capability Building, Measurement & Value Realization) that don't have
a dedicated role bundle in AI Accountability.

**Audit conducted:** July 3, 2026

**Scope:** Two new `evidence.yaml` entries (`ev-shrm-state-of-ai-hr-2026-upskilling-lead`,
`ev-fortune-cfo-ai-value-2026-substantial-value`) and one reused entry
(`ev-deloitte-cdo-survey-2025-governance-priority`, already verified and cited elsewhere in
this bundle).

**Summary verdict:** One confirmed misattribution, corrected before merge. Both new figures
and the reused figure are otherwise accurate.

---

## Findings

**CLAIM: "only 2% of companies assign CFOs [AI value] accountability... yet when they do,
76% achieve substantial value" — attributed to "Fortune (citing EY-Parthenon research)"**

> **Status: ❌ MISATTRIBUTED — corrected**

The Fortune article (fortune.com, March 27, 2026) attributes this research to the **Return
on AI Institute**'s study *"Economic Maturity for Artificial Intelligence"* (Laks
Srinivasan and Thomas H. Davenport; survey of 1,006 C-suite executives, 11 countries, 32
industries). "EY-Parthenon" does not appear anywhere in the source article. The 2%/76%
figures themselves are exact.

**Fix applied:** `source.org` in `evidence.yaml` and the rendered citation label corrected
to "Fortune (citing Return on AI Institute research)".

---

**CLAIM: "Upskilling and reskilling the workforce was the only area of AI implementation
where HR functions were close to taking the lead (28%)" — SHRM, *State of AI in HR 2026***

> **Status: ✅ VERIFIED**

Confirmed verbatim against the SHRM report (shrm.org). Note: the page's original wording
("28%, tied with cross-functional task forces") overstated the closeness — SHRM's own text
says HR fell just behind cross-functional task forces at 29%, not tied. Corrected to "just
behind cross-functional task forces at 29%."

---

**CLAIM: "51% of CDOs ranked data governance as their top priority" — Deloitte CDO Survey
2025**

> **Status: ✅ VERIFIED — pre-existing entry, reused unchanged**

Same figure and wording already verified for this bundle's Data Readiness track (see
[2026-06-12 audit](/enterprise-ai-transformation/validation/audits/2026-06-12-data-readiness.md)).
The new paragraph originally implied this came from "the same survey" as the CDAO
strategy-ownership stat cited earlier on the page — a dangling reference, since that
earlier stat is from a different source (MIT SMR/Wavestone and Gartner). Reworded to name
Deloitte's survey directly.

---

## What Was Confirmed — No Changes Needed

- SHRM 28% HR-upskilling figure (✅)
- Fortune/Return on AI Institute 2%/76% CFO-value figures (✅, after attribution fix)
- Deloitte 51% CDO governance-priority figure (✅, pre-existing)
- Cross-links from Program Architecture to the six AI Accountability role bundles (✅ —
  structural, not sourced statistics; verified all linked pages exist)

---

*Audit performed by Claude (One Step Labs) · July 3, 2026*
