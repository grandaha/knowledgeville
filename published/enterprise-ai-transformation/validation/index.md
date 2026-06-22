# Validation

We don't just publish research — we check it. Every statistic, external reference, and
sourced claim is independently verified, and each validation sweep is recorded below as a
dated audit. This is how we show the work, and how the base keeps improving over time.

**Most recent sweep:** 2026-06-22 — full-bundle provenance backfill (issues #48/#49).
**Coverage so far:** the **entire published bundle** — all eight tracks, the Running-the-Program
guides, the framework executive summary, and the glossary. Every statistic has been migrated to
the structured provenance store (**272 verified entries**), and two CI gates now enforce the
convention on every change.
**Current verdict:** broadly well-sourced and accurate. No fabricated statistics were found;
several dated claims, edition mix-ups, and Gartner/regulatory/vendor nuances were corrected,
and a handful of unsourceable figures were pruned or softened. Every claim-shaped number in the
bundle is now either traceable to a verified primary source or explicitly marked as a non-claim
(a recommended threshold, worked example, or statutory designation).

How sourcing works on each page: every verified claim is recorded in a structured provenance
store (`evidence.yaml`), cited inline as a followable anchored link to its entry
(`([Org, Year](#ev-…))`), and listed in a generated `## Sources` section at the foot of the page
— so any statistic reaches its primary source in two clicks or fewer. Two checks run in CI on
every change: `validate_okf.py --strict-citations` fails the build if any citation anchor does
not resolve to a ledger entry, and `check_uncited_numbers.py --strict` fails it if any
claim-shaped number sits in prose without an anchor (or an explicit `<!-- noev -->` exemption).
The audits below re-check the sources behind those claims.

See the dated records under **Audits**.

## In this section

| Page | Last updated |
| --- | --- |
| [Audits](audits/) | — |
| [Tracked Sources](tracked-sources.md)<br>Public registry of the recurring research franchises this knowledge base relies on — cadence, the edition currently cited, and when to check for a newer one. | Updated 2026-06-20 |
