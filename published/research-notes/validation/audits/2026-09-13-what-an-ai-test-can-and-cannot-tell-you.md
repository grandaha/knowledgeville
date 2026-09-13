---
type: Audit
title: "Citation Audit: What an AI Test Can and Cannot Tell You"
description: Validation of every cited number and quote in the research note on AI evals against its primary source.
tags: [audit, citations, validation, evals]
timestamp: "2026-09-13"
generated:
  by: human:daveraffaele
  at: "2026-09-13T00:00:00Z"
---

## Purpose

This record covers a check of every statistic, quote, and attribution in [What an AI Test Can and Cannot Tell You](/research-notes/what-an-ai-test-can-and-cannot-tell-you.md). Each claim was compared with its primary source: the arXiv papers, the Anthropic, OpenAI, GitHub, LangChain, Galileo and Raindrop pages, the NIST AI 600-1 profile, and the IMDA starter kit.

**Audit conducted:** September 13, 2026

**Updates completed:** September 13, 2026

**Scope:** the note and its 41 entries in this bundle's evidence ledger.

**Summary verdict:** no fabricated numbers and no misattributed organizations. The author's own sample-size arithmetic is correct. Five passages said slightly more than their sources, two moderately and three in minor ways. All five were corrected.

---

## Changes applied

- **Szymanski et al. (moderate).** The note presented the abstract's 68% and 64% as an inconsistency with the results section. The paper's Table 3 shows these are the agreement rates when the AI grader was told to act as an expert. The note and both ledger entries now say so.
- **Anthropic, 2026 (moderate).** The note said the April 2026 postmortem covers two changes. It covers three: an effort-setting change, a caching change, and a prompt change. The note now says three, two of which matter here.
- **Zhu et al. (minor).** The note glossed "up to 100% in relative terms" as a score reported at double its true value. That covers only overestimation. The gloss now covers both directions.
- **JudgeBench (minor).** The source says "many strong models" perform slightly better than random guessing. The note had dropped "many." Restored.
- **Anthropic, 2026 (minor).** The 3% drop came from one evaluation in a broader set, not the whole set. Reworded.
- **Sample-size arithmetic (optional nuance, applied).** The usual interval gives about 11 points either way at 50 cases and an 80% pass rate. The note now adds that methods suited to small samples give a wider range, consistent with the Bowyer et al. paper it cites.

## Verified correct

Zheng et al. Table 5 (first turn, with and without ties), Norman et al. (kappa deflation of 33 to 41 points on MT-Bench, rankings shifting up to 14 places, position bias in two production judges), Bavaresco et al., Gema et al., Northcutt et al., Humanity's Last Exam (about 18%), BenchJack (10 benchmarks, 219 flaws), Bowyer et al., Miller, Bean et al. (16.0%), van der Maden et al., the OpenAI sycophancy account (read from an archived copy), the Anthropic 2025 and 2026 postmortems, the Anthropic, OpenAI and GitHub guidance pages, NIST AI 600-1 actions MS-2.3-003 and MS-2.5-001, the IMDA starter kit, and the Galileo and LangChain survey figures. Every stake description checked out.
