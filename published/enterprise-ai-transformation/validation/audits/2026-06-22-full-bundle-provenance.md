---
type: Audit
title: Full-Bundle Provenance Backfill — June 2026
description: "Validation sweep migrating every statistic in the bundle to the verified evidence ledger, with both citation gates now enforced in CI."
tags: [audit, citations, validation, provenance]
timestamp: "2026-06-22"
---

## Purpose

This record documents the **full-bundle provenance backfill** — the sweep that took every
statistic, external reference, and sourced claim across the entire knowledge base and migrated it
into a structured, independently verified evidence ledger
([`evidence.yaml`](/enterprise-ai-transformation/validation/index.md)), then turned on CI
enforcement so the convention can no longer silently regress. It is the successor to the June 12
[Data Readiness audit](/enterprise-ai-transformation/validation/audits/2026-06-12-data-readiness.md),
which covered one track; this sweep covers **all of them**.

**Audit conducted:** June 19–22, 2026 (building on the evidence-infrastructure work of June 20).

**Scope:** the **entire published bundle** — the framework executive summary, all eight tracks
(01 Strategy & Leadership, 02 Governance & Risk, 03 Data Readiness, 04 Technology Architecture &
Platform, 05 Workflow Optimization & Automation, 06 Adoption & Culture, 07 Talent & Capability
Building, 08 Measurement & Value Realization), the Running-the-Program guides, and the glossary.

**Summary verdict:** the knowledge base is **broadly well-sourced and accurate**. Across the sweep,
**272 discrete claims** were verified against their primary sources and recorded in the ledger. **No
fabricated statistic survived** — but several were caught and removed at the source: a fabricated
"Deloitte: organizations scoring >70% on readiness are 3× more likely to succeed" (no such report
exists; the AI Readiness Index is Cisco's), a misquoted "Gartner: 85% of AI failures are
attributable to data" (the real 2018 figure was about biased outcomes, not failure rates), and a
"Gartner: 35% of large enterprises will have a CAIO by 2025" prediction that appears in no Gartner
primary. Beyond outright removals, the sweep corrected numerous edition mix-ups, attribution-chain
errors, scope/wording imprecisions, and stale forward-looking framings, and pruned roughly a dozen
unsourceable vendor/aggregator figures. Every claim-shaped number in the bundle is now either
traceable to a verified primary source or explicitly classified as a non-claim (a recommended
threshold, worked example, scoring-rubric band, or statutory cap cited by official designation).

---

## What changed — from inline labels to a verified ledger

Before this sweep, sources were cited as inline `(Org, Year)` labels, with a hand-written `## Sources`
list at the foot of each page. That convention couldn't be checked: a label could be misattributed,
an edition could drift, and a bare number in narrative prose could carry no source at all without
anything flagging it.

The backfill replaced that with a structured provenance layer:

- **Every verified claim is now an entry in the evidence ledger** (`validation/evidence.yaml`),
  carrying the exact figure, the wording it supports, its primary source (organization · report ·
  edition · URL), a verification date, and a status (`primary`, `secondary-mirror` where the
  publisher domain blocks automated fetching but the figure was confirmed via press release plus
  corroboration, or `blocked` where the primary could not be reached).
- **Inline citations became followable anchored links** — `([Org, Year](#ev-…))` — so any statistic
  reaches its primary source in two clicks or fewer.
- **The `## Sources` list at the foot of each page is now generated** from those anchors, not
  hand-maintained.
- **Two CI gates now enforce the convention on every change** (turned on at the close of this
  sweep): `validate_okf.py --strict-citations` fails the build if any citation anchor does not
  resolve to a ledger entry, and `check_uncited_numbers.py --strict` fails it if any claim-shaped
  number sits in prose without an anchor (or an explicit `<!-- noev -->` exemption for a documented
  non-claim).

The ledger itself is the canonical per-claim record. This document is the **narrative sweep
record** — what was covered, what was corrected, and what was pruned.

---

## Coverage and ledger growth

The sweep ran section by section, each verifying claims against primaries and recording new ledger
entries (reusing existing entries wherever a recurring franchise — McKinsey *State of AI*, BCG's AI
value series, Gartner, IBM, Deloitte — had already been verified):

| Section | Citations migrated | New verified ledger entries |
| --- | --- | --- |
| Framework executive summary | 16 | +12 (seeded the recurring franchises) |
| Track 06 — Adoption & Culture | 73 | +40 |
| Track 07 — Talent & Capability Building | 58 | +18 |
| Track 08 — Measurement & Value Realization | 84 | +29 |
| Running the Program | 85 | +27 |
| Track 05 — Workflow Optimization & Automation | ~90 (two passes) | +44 |
| Track 04 — Technology Architecture & Platform | ~18 (two passes) | +16 |
| Track 03 — Data Readiness | ~55 (multiple passes) | +44 |
| Track 02 — Governance & Risk | 20 | +17 |
| Track 01 — AI Strategy & Leadership | ~30 | +23 |
| Glossary + cross-track stragglers | 2 (reuse) | 0 (classification only) |
| **Total** | **≈530** | **272 ledger entries** |

A second, complementary pass — driven by a new uncited-number linter built during the sweep — caught
a structural blind spot: the first backfill keyed on *italic* `*(Source, Year)*` citations, so it had
silently skipped every page that cited sources in **non-italic** `(Source, Year)` narrative prose
(notably across Tracks 03, 04, and 05). Closing that gap added the final entries and brought the
linter to **zero findings across the bundle**.

---

## Material corrections, by section

The substantive findings — the corrections that changed what a reader sees, beyond mechanically
anchoring an already-correct citation.

**Framework executive summary.** Four precision corrections from the verification pass: the McKinsey
*Superagency* "1% mature" figure had been misattributed; the 39% impact figure was qualified to
"enterprise-level EBIT impact"; the high-performer figure was stated as "5% or more"; and BCG's "~60%"
was scoped to "little or no value."

**Track 01 — AI Strategy & Leadership.** The densest track and the best-sourced — **zero prunes**,
every claim verified to a primary. Corrections: Prosci's sponsorship multiplier was overstated as
"~6×" → corrected to Prosci's actual **3.5×** (extremely-effective vs. very-ineffective sponsorship);
Gartner spending split into two distinct entries ($644B GenAI, March 2025; $1.5T total AI, September
2025 — different press releases); BCG's "5× greater financial impact" clarified as **per use case**,
not aggregate; the McKinsey "3× senior-leader ownership" claim separated from the high-performer
entry as a distinct figure.

**Track 02 — Governance & Risk.** Materially better sourced than Track 03 (16 of 17 claims verified,
one prune), but several re-attributions: "66% of boards have limited AI knowledge" was credited to
*Corporate Compliance Insights* but is really **Deloitte Global** (CCI was republishing); the Stanford
HAI incident counts conflated two AI Index editions → split into 2025 (233) and 2026 (362); IBM "97%
lack AI access controls" rescoped to "97% **of breached orgs**"; the EU AI Act €15M/3% penalty
relabeled from "high-risk violations" to the correct operator-obligations scope. **Pruned:** Gartner
"35% of large enterprises will have a CAIO by 2025" — unfindable in any Gartner primary (the IBM IBV
26%/11% CAIO figures were verified and kept).

**Track 03 — Data Readiness.** The largest cleanup, because the track leaned on vendor blogs and
several bare attributions. **Removed (no valid source / misquote / circular vendor marketing):** the
fabricated "Deloitte 3× success above 70% readiness" (→ restated to Cisco's verified 13%-fully-ready);
the misquoted "Gartner 85% of AI failures attributable to data" (→ RAND 2024 ">80% of AI projects
fail"); a garbled "BCG 10% budget → 1.5× success" (→ BCG's real **10-20-70** rule); DATAVERSITY "61%
bias-detection gap" (a misquote laundered via Atlan); and several SEO/aggregator citations (Gitnux,
Quinnox, Ranktracker, Azumo). **Re-attributed to true primary:** "$3.1T data-quality cost" to IBM/HBR
2016 (not Gartner); "80% of ML effort" to Cognilytica 2020 (not IBM); "25% revenue loss" to MIT Sloan
(Redman) with the figure corrected to the real **15–25%** range. **Verified new primary** (gap pass):
the data-poisoning research on the security page — poisoning **0.1%** of a 100B-token corpus embeds
persistent backdoors — traced to **Zhang et al., *Persistent Pre-Training Poisoning of LLMs*
(arXiv:2410.13722, 2024)**, with the prose scope corrected to "model sizes up to 7 billion parameters."
An unsourced "78% have not solved machine unlearning" was softened to remove the false precision. The
data-audits page was confirmed to be **authored methodology** (recommended thresholds, worked examples,
tool pricing) rather than sourced statistics, and its figures classified as non-claims accordingly.

**Track 04 — Technology Architecture & Platform.** The FinOps Foundation metric was corrected from
"tracking or managing" to the source's actual "**managing** AI spend" (63%, up from 31%). In the gap
pass, three parallel verification agents confirmed the platform/vendor stats; the IBM Cost-of-a-Breach
shadow-AI figures were checked carefully — IBM's 2025 global-average breach cost actually **fell** to
$4.44M, and the page correctly cites only the **+$670K shadow-AI delta** above that average, not a
bogus baseline.

**Track 05 — Workflow Optimization & Automation.** RPA scaling was stated as "3–4%" but Deloitte's
2018 survey says **about 3%** → corrected; Deloitte's 25%/30% production-redesign figures were the
**2026** edition, not the cited 2025 → re-anchored and relabeled. In the gap pass, an unverified
"Gartner-via-PEX $872M→$2B process-mining market" aside and an unverified "MarketsandMarkets 45.6%
CAGR" clause were **dropped** (the verified Deloitte and Fortune Business Insights figures on the same
lines carry the point).

**Track 06 — Adoption & Culture.** Edition-honesty calls captured rather than silently upgraded: the
McKinsey 78% adoption figure was anchored to the **2024** edition (the page itself says "up from 55% in
2023"), so freshness tooling surfaces it as a prior edition; BCG's 10-20-70 was anchored to the
canonical 2024 source even where pages' prose mis-dated it 2025.

**Track 07 — Talent & Capability Building.** Deloitte's "Skills-Based Organization" research was dated
2024 in the pages but is **2022** → corrected on ids and link labels; MIT CISR came back richer than
cited (62% in the first two of four stages, n=721).

**Track 08 — Measurement & Value Realization.** Brynjolfsson's customer-support study was updated to
the **QJE 2025** edition (15%/30%, n=5,172), superseding the 2023 NBER working-paper figures
(14%/34%); the Deloitte "State of GenAI" waves were pinned to their correct quarterly editions.

**Running the Program.** The Goldman Sachs SMB resource-gap figure — the share of small-business
owners who say they lack the resources and expertise to deploy AI — was stated as "~42%" but the
primary says **44%** → corrected; a McKinsey "one-third vs. one-in-ten measurement" split could not be pinned to a public
quote → its ledger entry is marked **blocked** (and renders a "primary source unreachable" note rather
than asserting a figure we couldn't confirm); a KPMG 83% assurance figure was confirmed only as the
**Australia** snapshot and flagged as such.

**Glossary + cross-track stragglers.** Two figures reused existing ledger anchors (BCG's "5% at scale";
the Rogers/Moore ~16% diffusion-chasm threshold); the remainder were classified as non-claims —
statutory caps cited by official designation (GDPR €20M/4%, CCPA $2,500/$7,988), definitional
illustrations, and worked-example arithmetic.

---

## What this hardens going forward

At the close of the sweep, both provenance checks were flipped from advisory to **blocking** in CI. A
new page that states a statistic without anchoring it, or anchors it to a ledger entry that doesn't
exist, is now rejected before merge. Combined with the recurring-source registry
([`sources.yaml`](/enterprise-ai-transformation/validation/index.md)), which tracks the edition the
bundle cites for each franchise and flags when one is aging, the base now maintains its own provenance
rather than relying on periodic manual audits.

**Flagged for future sweeps** (verified-honest gaps, not errors):

- A **regulatory-claims pass** — several non-statistical regulatory instruments (e.g. SR 26-2's "April
  2026" date, NYDFS Circular 2024-7) are cited by official designation but predate this verification
  sweep and were not re-checked in it.
- A **secondary→primary upgrade pass** for entries currently marked `secondary-mirror` because the
  publisher domain blocked automated fetching.
- Relabeling the McKinsey 2024-adoption edition entry where it sits behind the current 2025 figure.

---

*Audit performed by Claude (One Step Labs) · June 19–22, 2026. Per-claim verification detail lives in
the evidence ledger; this record is the narrative summary of the sweep.*
