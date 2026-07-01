---
type: Reference
title: What's Changed
description: A generated, release-by-release record of how this knowledge base has changed.
tags: [changelog, releases, provenance]
timestamp: "2026-07-01"
appendix: true
---

<!-- generated from GitHub Releases by scripts/build_changelog.py — do not edit -->

This page records how this knowledge base has changed over time — new and expanded content, citation corrections, freshness updates, and structural changes — captured release by release. *How the knowledge changed is itself a form of provenance.*

## v5.3.1 — 2026-07-01

## Site & structure

- Tidied the AI Briefs navigation: the two areas now read **Research Briefs** and **Industry Briefs** under the AI Briefs heading, instead of repeating "AI" in each.

## v5.3.0 — 2026-07-01

## Site & structure

- **The two brief bundles are now one: [AI Briefs](https://knowledge.onesteplabs.com/ai-briefs/).** Research Briefs (papers) and Industry Briefs (analyst and market commentary) now live together under a single AI Briefs area, instead of two separate top-level entries. Each keeps its own focus and sourcing; the top level is simpler. Old links are redirected to the new locations, so existing bookmarks keep working.

## v5.2.1 — 2026-07-01

## Fixes

- Tightened source fidelity across three recent additions: restored a verbatim quote of the OKF specification, corrected two citation/attribution details in the Aaron Levie industry brief, and reworded an AI Playbooks setup note so it no longer claims a capability for specific named products.

## v5.2.0 — 2026-07-01

## New & expanded content

- **AI Use Cases — AI Playbooks** — a new sub-domain of agent-executable playbooks: procedures an AI assistant reads and runs on its own across your email and calendar, rather than prompts you paste. Six to start — Morning Brief, Inbox Triage, Meeting Prep, Weekly Review, Follow-up Tracker, and End-of-Day Wrap — each with numbered steps for the assistant, an example of what it produces, and read-first guardrails (it reads and drafts, but never sends, deletes, or changes anything).

## v5.1.0 — 2026-07-01

## New & expanded content

- **AI Industry Briefs — Enterprise AI Is Not a Startup** — a new Market and Adoption brief on Aaron Levie's (Box CEO) argument, via HFS Research: enterprise AI is constrained by workflow, data, and accountability — not model quality — and the real transformation lives in the ~88% of the economy that does not run like a tech startup. Levie's figures are flagged as forward projections, with both the CEO's and the analyst's commercial stakes noted.

## v5.0.2 — 2026-07-01

## Fixes

- Industry brief source links now show the full source URL instead of just the domain, so the exact article a brief is based on is visible at a glance.

## v5.0.1 — 2026-07-01

## Site & structure

- Refreshed the homepage **Where to start** guide to route by intent across the current knowledge base — begin with the Open Knowledge Format, copy a ready-to-run recipe, read the enterprise model, follow the research and industry briefs, or connect the whole base over MCP.

## v5.0.0 — 2026-07-01

## New & expanded content

- **Open Knowledge Format** — a new bundle explaining OKF, the open format this whole knowledge base is built on, for knowledge and strategy leaders. Two arcs across seven pages:
  - **Understanding OKF** — what OKF is, how it works, where it fits against RAG, knowledge graphs, and plain docs, and how it handles provenance.
  - **The Potential** — our grounded read of where it could go: knowledge for agents, the honest gaps in v0.1, and whether the direction fits you.

  Facts are grounded in the canonical OKF specification; the forward-looking half is our analysis, marked as such.

## Site & structure

- **Open Knowledge Format now leads** the knowledge base — first in the bundle list on the homepage and first in the site navigation, since it is the format everything else is built on.

## v4.2.0 — 2026-07-01

## New & expanded content

- **AI Industry Briefs — The Great Value Migration** — a new brief, and a new **Strategy & Investment** theme in the AI Industry Briefs. It's a plain-language read of an investor's thesis that as AI gets cheap, value shifts from *selling* compute to *owning and orchestrating* it — favoring the big cloud platforms. Every borrowed figure is traced to its original source, and the author's disclosed stock positions are flagged as stake, not advice.

## Site & structure

- **Connect over MCP** — the homepage now shows a third way to use Knowledgeville: point any AI assistant at the live knowledge base over the Model Context Protocol, at `https://www.onesteplabs.com/knowledgeville/mcp`. Alongside reading it as a site and cloning the GitHub repo.
- The **AI Industry Briefs** area is now listed on the homepage bundle index.

## v4.1.0 — 2026-07-01

## New & expanded content

- **Realtors** — a new set of plain-language, paste-ready AI recipes for real-estate agents, joining Everyday Tasks and Executive Leadership under AI Use Cases. Nine recipes across three areas:
  - **Listings & Marketing** — write a listing description, just-listed/just-sold social posts, and an open-house promo kit.
  - **Prospecting & Outreach** — neighborhood farming letters, expired and FSBO scripts, and referral asks to your sphere.
  - **Client Communication** — buyer and seller follow-ups, plain-language explainers for offer terms, and review requests.

Each recipe hands you a prompt, shows a real before-and-after, and flags where an agent must keep control — fair-housing language, do-not-call and texting rules, and the line between explaining a term and giving legal advice.

## Site & structure

- New **Realtors** area under AI Use Cases, with its own three-section map.

## v4.0.0 — 2026-06-30

## New & expanded content

- **AI Industry Briefs** — a new area of plain-language briefs on what analysts and the market are saying about AI, written for business leaders. The companion to AI Research Briefs: where those cover academic papers, these cover analyst, vendor, and market commentary.
- **The AI Adoption Gap** — the first brief, a read of an HFS Research thesis on why AI's market valuations have run ahead of real enterprise adoption, and what leaders should do about it.

## Site & structure

- New top-level **AI Industry Briefs** section, opening with its first theme, **Market and Adoption**. Each brief states plainly who is making a claim and what they stand to gain, so you can weigh it yourself.

## v3.0.0 — 2026-06-29

### New & expanded content
* **AI Research Briefs** — a new bundle of plain-language briefs of notable AI research papers, written for business leaders and knowledge workers: what each paper found, how much to trust it, and what it means for you.
* **There's No Silver Bullet for Coding-Agent Rewards** — why no single reward keeps a coding agent honest, and what a layered verification stack does instead.
* **Why AI Drops Its Caution the Moment You Ask for Advice** — AI models assert cause-and-effect when asked for advice that they'd carefully hedge under analysis, and a one-line re-prompt brings the caution back.

### Site & structure
* New **AI Research Briefs** area on the site, grouped by theme (Agents & Tool Use, Reasoning & Capabilities), with a guide to how each brief is structured and how to read its trust assessment.

## v2.1.1 — 2026-06-29

### New & expanded content
* Plain-language readability pass on everyday-tasks (20-page audit)

## v2.1.0 — 2026-06-28

### New & expanded content
* Executive-leadership sub-domain bundle (design + scaffold, 16 planned stubs)
* Author draft-a-board-update (first executive-leadership page)
* Author prep-board-investor-qa (first workflow-shape page)
* Author remaining 14 executive-leadership pages (bundle complete 16/16)
* Surface Executive Leadership on the homepage

## v2.0.0 — 2026-06-25

### New & expanded content
* Reframe a top-level domain as a "knowledge bundle", not a "framework"
* Ai-use-cases domain + everyday-tasks bundle (20 demo-first pages)
* Surface AI Use Cases on the homepage

### Site & structure
* Add the Maturity Self-Assessment tool to the site nav

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
