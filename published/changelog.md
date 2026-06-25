---
type: Reference
title: What's Changed
description: A generated, release-by-release record of how this knowledge base has changed.
tags: [changelog, releases, provenance]
timestamp: "2026-06-25"
appendix: true
---

<!-- generated from GitHub Releases by scripts/build_changelog.py — do not edit -->

This page records how this knowledge base has changed over time — new and expanded content, citation corrections, freshness updates, and structural changes — captured release by release. *How the knowledge changed is itself a form of provenance.*

## v2.0.0 — 2026-06-25

### New & expanded content
* Reframe a top-level domain as a "knowledge bundle", not a "framework"
* Re-run #3: AI Use Cases through the hardened funnel (closes C1 + C7)
* Clear AI Use Cases test content for a clean-slate funnel run
* Ai-use-cases domain + everyday-tasks bundle (20 demo-first pages)
* Surface AI Use Cases on the homepage

### Structural & tooling
* Clean up the generated changelog rendering
* Add the Maturity Self-Assessment tool to the site nav
* Move assessment tool under the Enterprise AI Transformation section
* Place assessment tool above the glossary in the section nav
* Richer assessment results (profile-shape read) + cross-link Integrated Assessment
* Move maturity tool out of the OKF bundle (host on onesteplabs.com)
* Split Maturity Model out of Framework Architecture
* Publish gate — keep unfinished (planned) content off the live site
* Funnel-improvement roadmap (forcing-function findings → fixes → re-run)
* Tooling: LAN-accessible publishable-site preview (scripts/preview.py) [#106]
* Carve out the scaffold-location exception in CLAUDE.md [#109]
* Tooling: scaffold H1-dup fix + publish-completeness check [#108 partial]
* Spec-driven authoring funnel — design (#107)
* Research-profile + temporal-mode — design & #107 reconciliation (#56)
* Plan: research-profile build (#56)
* Research-profile.yaml + validation (#56)
* Bundle scaffolder (new_bundle.py) — design (#108)
* Plan: bundle scaffolder build (#108)
* Bundle scaffolder (new_bundle.py) (#108)
* Spec.yaml + calcification-guard check — design (#107-A)
* Plan: spec.yaml guard build (#107-A)
* Spec.yaml + calcification-guard check (#107-A)
* Design: /design-domain emits the spec (#107-B)
* /design-domain emits the spec (#107-B)
* Design: /author-concept consumes the spec (#107-C)
* /author-concept consumes the spec (#107-C)
* Rubric: pre-registered eval for re-run #2 (#107)
* Design: scaffolder + back-matter hardening (re-run #2 friction)
* Scaffolder + back-matter hardening (closes re-run #2 friction)
* Local pre-push conformance gate + Actions-availability check
* Design: nested sub-domain bundles (#139)
* Nested sub-domain bundles: profile-rooted discovery (#139)

## v1.1.0 — 2026-06-22

### New & expanded content
* Interactive Maturity Self-Assessment tool, generated from the assessments (#88)

### Structural & tooling
* SemVer releases + de-emoji the changelog
* Exclude overview.md from the distributed bundle (OKF alignment)

## v1.0.0 — 2026-06-22

Initial release of the Knowledgeville knowledge base.

### Frameworks in this release

**Enterprise AI Transformation** — a complete eight-track framework for taking an organization from AI ambition to measured value, plus a *Running the Program* section that ties the tracks together into an assessment, a sequencing model, and a 90-day launch:

- AI Strategy & Leadership
- AI Governance & Risk
- Data Readiness
- Technology Architecture & Platform
- Workflow Optimization & Automation
- AI Adoption & Culture
- Talent & Capability Building
- Measurement & Value Realization

Every statistic on every page is backed by a verified primary source in the evidence ledger, traceable in two clicks, and enforced in CI.

Read it at <https://knowledge.onesteplabs.com/enterprise-ai-transformation/>.

### What's next

Future releases record what changed since the last one — grouped as new & expanded content, citation corrections, freshness updates, and structural & tooling changes — so returning readers can see what's new as more domains and topics are added.
