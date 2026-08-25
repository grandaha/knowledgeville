---
type: Reference
title: What's Changed
description: A generated, release-by-release record of how this knowledge base has changed.
tags: [changelog, releases, provenance]
timestamp: "2026-08-25"
appendix: true
---

<!-- generated from GitHub Releases by scripts/build_changelog.py — do not edit -->

This page records how this knowledge base has changed over time — new and expanded content, citation corrections, freshness updates, and structural changes — captured release by release. *How the knowledge changed is itself a form of provenance.*

## v12.0.0 — 2026-08-25

## Knowledgeville is now an OKF v0.2 knowledge base

The [Open Knowledge Format](https://github.com/GoogleCloudPlatform/knowledge-catalog/blob/main/okf/SPEC.md) released v0.2, and this knowledge base has moved to it. The headline change is that **provenance is now part of the format itself**, not just a local habit.

### Every page now carries machine-readable provenance

Open any page's source and you will find, in its frontmatter:

- **`generated`** — which model wrote it, and when it last meaningfully changed
- **`verified`** — who checked its claims against their primary sources, and on what date
- **`sources`** — the sources behind the page, as structured data rather than only a list at the bottom
- **`stale_after`** — a freshness horizon, where every source behind the page carries one

An agent or a person reading a bundle can now ask what has been checked, and by whom, without trusting a summary. Across the published bundle that resolves to **103 pages human-reviewed** and **105 unverified** — the honest split, not a target. A page with no cited evidence carries no verification claim, because in OKF an absent field means something.

### Two pages were wrong, and v0.2 is why

The OKF bundle explains the format, and it had predicted this direction. Its own words:

> *"There is no standardized verification or trust layer, so a reader cannot check a bundle's claims through the format itself."*

That gap is now closed, so both pages that described it have been rewritten:

- **[Provenance and Trust](https://knowledge.onesteplabs.com/open-knowledge-format/01-understanding-okf/03-provenance-and-trust/)** — said none of our verification practice was required by the format. The spec has since moved toward it.
- **[Where OKF Could Go](https://knowledge.onesteplabs.com/open-knowledge-format/02-the-potential/02-where-okf-could-go/)** — its "gaps today" section now records what v0.2 closed and what is still open.

The distinction that survives, and is now the honest open question: the format records *that* a check happened. It cannot tell you the check was any good. "Verified" remains the publisher's assertion, and a reader still has no way to weigh one publisher's against another's.

### Two rendering corrections

A parser fault had been corrupting two live pages:

- **[Decision Guides](https://knowledge.onesteplabs.com/decision-guides/)** — a listing showed `\"forward deployed\"` with literal backslashes
- **[The Talent Obsession](https://knowledge.onesteplabs.com/ai-briefs/industry-briefs/workforce-and-skills/the-talent-obsession/)** — a quoted source line had lost its closing quotation mark

Both now render as written.

## v11.1.2 — 2026-08-24

### Corrections

A sweep for unsourced claims turned up a pattern the existing checks could not see: assertions that are load-bearing but contain no number, so nothing flagged them.

**[Access & Integration](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/04-access-and-integration/) now credits Deloitte for a passage that was presented as anonymous consensus.** The paragraph describing the data architecture AI leaders are converging on read as "the 2026 consensus" with no source. It is a near-verbatim paraphrase of Deloitte's State of AI in the Enterprise 2026 — a survey of 3,235 leaders across 24 countries — which is now verified and cited.

**Two further "2026 consensus" claims are gone.** A second passage on that page, and one in [Data Mesh Governance in Practice](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/data-mesh-governance-in-practice/), asserted a consensus sourced to "multiple implementation reports" or to nobody at all. Both now read as what they always were: this framework's recommendation.

**[AI Governance & Risk](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/01-executive-summary/) drops an invented figure.** It claimed most enterprises run governance "three to four years behind" their AI deployments. Nothing supported that number. The point it was making — that governance is routinely stood up after the AI it governs — stands without it.

**[The AI Governance Framework](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework/) no longer opens on an unsourced proportion.** It asserted what share of enterprise AI is assembled from third-party components. The concrete list that follows makes the case without needing a measured figure.

## v11.1.1 — 2026-08-23

### Cleanup

**Four pages lose a trailing glossary block that pointed nowhere.** [Lineage & Metadata](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata/), [Data Governance](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/03-data-governance/), [Infrastructure Readiness](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/05-infrastructure-readiness/) and [Security & Compliance](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/06-security-and-compliance/) each ended with a list of bolded terms telling you to see the glossary, with no link — and the glossary defined none of the terms named. Each page already defines those terms where you meet them, which is where they belong.

**The [Glossary](https://knowledge.onesteplabs.com/enterprise-ai-transformation/glossary/) now links to the pages its terms come from.** Its section introductions referred to "Component 02" through "Component 06", numbering from an earlier structure that no longer matched any page.

### Corrections

**[Lineage & Metadata](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/02-lineage-and-metadata/) drops two unsourced passages** — one asserting what most enterprises had realised by 2026, one asserting what enterprises reporting AI value had done. The AI context layer section now explains what actually distinguishes a context layer from a catalog: an agent queries it mid-task, so it cannot afford the staleness a catalog can.

**Its tooling table no longer carries an analyst award in the suitability column.** The award was accurate but held by more than one vendor in the same table, and that column describes fit.

## v11.1.0 — 2026-08-23

### New & expanded content

**Expanded — [Data Audits & Automated Quality Governance](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/03-practitioner-guides/data-audits-and-automated-quality-governance/)** — the audit walkthrough now covers all six quality dimensions instead of two. New steps for consistency, timeliness, validity and uniqueness, each with its audit techniques, a scoring formula and a threshold. A new step covers the composite score: how to pick dimension weights from your use case's failure mode, the formula, a worked example, and the thresholds in one table.

The worked example is deliberately a failing one. A dataset scores 84.0 overall and is still unfit for production AI use, because three dimensions sit below their blocking gate and the composite shows none of that.

### Corrections

**[Data Quality](https://knowledge.onesteplabs.com/enterprise-ai-transformation/tracks/03-data-readiness/02-framework/01-data-quality/) — the six dimensions were credited to the wrong source.** They come from a DAMA UK working group paper of October 2013, not from DAMA-DMBOK, which is a separate and broader publication. There is also no canonical list of six: DAMA's Dutch chapter distilled 60 preferred dimension definitions from 127 across nine authoritative sources. The page now says both, cited.

**Quality thresholds are now stated as recommendations, not standards.** No standards body publishes them. ISO 8000-8:2015 says directly that establishing a threshold is the organisation's job and that the standard does not set one. Both pages now say so and tell you to set your own against the consequence of failure, and to write down the reasoning.

**A contradiction between the two pages is resolved.** The framework page blocked any dataset scoring below 70 on a dimension, while the audit guide blocked accuracy below 90. The audit guide's per-dimension gates are now the single set, and the scoring section links to them — previously it named a scoring approach with no way to reach the method behind it.

## v11.0.0 — 2026-08-10

### New & expanded content

**New bundle — [Research Notes](https://knowledge.onesteplabs.com/research-notes/)** — working notes on questions that are still open. Everything else here is finished and meant to be relied on; these are sourced findings published while the conclusion is still unsettled. Every number is still cited and verified.

**New note — [Why Your AI Gives Three Different Answers](https://knowledge.onesteplabs.com/research-notes/why-your-ai-gives-three-different-answers/)** — three executives ask an AI assistant how many active customers the company has and get three numbers, because Finance, Sales and Support each define "active" correctly for their own job. On what the word *ontology* is currently sold to solve, which version of that work has a track record, and where the evidence runs out.

Two corrections it records, both against primary sources: the Open Semantic Interchange specification's first release was **v0.1**, not the v1.0 several write-ups report, and it has since moved to the Apache Incubator as **Apache Ossie**.

## v10.4.0 — 2026-08-04

### New & expanded content

**New brief — [The Talent Obsession](https://knowledge.onesteplabs.com/ai-briefs/industry-briefs/workforce-and-skills/the-talent-obsession/)**

A read of TechCrunch's report that enterprise AI's bottleneck has moved from the model to the engineer who deploys it, and that only about 2,000 US engineers qualify.

The brief separates two layers the coverage blurs. The structural claim is checkable elsewhere: two frontier labs stood up services arms. The figures are not — every one comes from the executive search firm that places these engineers, from a study whose data sources are named but whose full text sits behind a request form. The shortage turns out to be a definition rather than a count, and the firm setting that threshold sells the scarce thing.

Companion to [When to Embed an Engineer](https://knowledge.onesteplabs.com/decision-guides/when-to-embed-an-engineer/), which covers the hiring decision itself.

## v10.3.0 — 2026-08-04

### New & expanded content

**New guide — [When to Embed an Engineer](https://knowledge.onesteplabs.com/decision-guides/when-to-embed-an-engineer/)**

For leaders whose AI pilots demo well and stall before production, and who have been told to hire a "forward deployed engineer." The guide is built around the decision rather than the job title: embed an engineer, hire a firm, or fix the handoff.

It covers the scope condition that makes embedding worth its cost, why deep context usually beats a fast start for internal work, who maintains what gets built, and the compensation and reporting-line traps that surface only after a search has already run. Every source quoted sells embedding in some form, and the guide says so at each point of use.

## v10.2.0 — 2026-07-11

### New & expanded content
* Author The Great Decoupling industry brief

## v10.1.0 — 2026-07-11

### New & expanded content
* Author MCP and the Context Gap

### Citation corrections
* Correct overstated MCP-governance-is-unprecedented claim

## v10.0.0 — 2026-07-07

### New & expanded content
* Author Why Dumping a File Rarely Works for AI-Assisted Data Analysis
* Author Preparing Your Data Before You Ask for AI-Assisted Data Analysis
* Author Code Interpreters vs. Plain Chat
* Author A Landscape of AI Data Analysis Tools, completing track 1
* Author Asking Good Analytical Questions
* Author From Raw Numbers to a Defensible Conclusion
* Author Where AI Fabricates Data and Numbers
* Author Silent Arithmetic and Logic Errors, completing track 2
* Author Building a Method, Not a Lucky Prompt
* Author Testing Your Method on a New Dataset, completing the bundle
* Refine and correct four pages in AI-Assisted Data Analysis after a full editorial review of the finished bundle

### Site & structure
* Scaffold AI-Assisted Data Analysis bundle
* Reframe AI-Assisted Data Analysis from 5 tracks to 3
* Surface AI-Assisted Data Analysis on the homepage

## v9.5.0 — 2026-07-06

### New & expanded content

* **New bundle: AI-Assisted Software Development.** The two real questions a developer or team lead faces with AI coding agents — does it actually make you faster, and does it open you up to new attacks. Covers the contested productivity evidence (a randomized controlled trial found AI coding tools slowed experienced developers down even as they believed it sped them up, set against vendor-reported speedups on simpler tasks) in [Does AI Coding Actually Help?](https://knowledge.onesteplabs.com/ai-assisted-software-development/01-does-ai-coding-actually-help/), and the named, documented vulnerabilities and supply-chain campaigns already targeting AI coding assistants in [Securing the AI Coding Workflow](https://knowledge.onesteplabs.com/ai-assisted-software-development/02-securing-the-coding-workflow/). ([#247](https://github.com/grandaha/knowledgeville-workspace/pull/247), [#248](https://github.com/grandaha/knowledgeville-workspace/pull/248), [#249](https://github.com/grandaha/knowledgeville-workspace/pull/249))

## v9.4.0 — 2026-07-06

### New & expanded content
* Name and map competing agentic-AI framework acronyms in workflow-optimization guide

## v9.3.1 — 2026-07-06

_No reader-facing knowledge changes in this release — wording polish only._

## v9.3.0 — 2026-07-06

### New & expanded content
* **Who Owns the Codified Judgment** (ai-native-organization) — a new page asking who owns a firm's judgment once it's codified well enough for an AI agent to apply it, and who's exposed when a firm buys that judgment rather than building it in-house. https://github.com/grandaha/knowledgeville-workspace/pull/240
* **Verify AI's Facts and Citations** (everyday-tasks) — a new recipe for checking an AI's claims and sources before relying on them, grounded in real hallucination-rate studies rather than a generic "always verify" caution. https://github.com/grandaha/knowledgeville-workspace/pull/241
* **Build vs. Buy** (decision guides) adds a new section on AI systems specifically — vendor dependency even when fine-tuning, per-token billing instead of a flat subscription, and the ongoing burden of evaluating factually wrong output that traditional software doesn't carry. https://github.com/grandaha/knowledgeville-workspace/pull/235
* **Explain a Concept Simply** (everyday-tasks) — the prompt now tells the AI to say so instead of forcing an analogy when none fits, and to flag anything experts still debate; the caveat now names the actual risk (a fluent but wrong analogy on a topic that feels like general knowledge but is actually contested). https://github.com/grandaha/knowledgeville-workspace/pull/239
* **Building Yours Without an Engineer** (team second brain) now states plainly it's an untested design, not a validated practice — the setup steps stay, but the page no longer implies this has been proven at team scale. https://github.com/grandaha/knowledgeville-workspace/pull/234

## v9.2.1 — 2026-07-05

### New & expanded content
* Rewrite Knowledgeville welcome intro in Dave's voice
* Add Team Second Brain to the homepage bundle list

### Site & structure
* Fix team-second-brain page order to match narrative sequence

## v9.2.0 — Team Second Brain bundle — 2026-07-05

### New & expanded content
* Author The Single-Player Ceiling as a decision-aid reference
* Author Building Yours Without an Engineer, completing team-second-brain

### Citation corrections
* Correct overstated single-user claim on team-second-brain lead page
* Add GitHub ecosystem evidence as phase-one history

### Site & structure
* Scaffold the Team Second Brain bundle

## v9.1.0 — Data Readiness reframed around the use case — 2026-07-03

### New & expanded content
* Open the Data Readiness framework with a use-case diagnostic
* Re-scope the AI Readiness Assessment to the use case, not the org
* Reposition Data Readiness framework pages around the use case
* Relabel practitioner guides around use-case scope

## v9.0.0 — The AI-Native Organization bundle — 2026-07-03

### New & expanded content
* Author The Three Accountabilities and The Partnership Pyramid, Generalized

### Site & structure
* Scaffold ai-native-organization bundle

## v8.1.0 — 2026-07-03

### New & expanded content
* Connect Enterprise AI Transformation's roles to AI Accountability

## v8.0.1 — 2026-07-03

### Site & structure
* Reorder AI Accountability roles into hierarchy, tighten overview

## v8.0.0 — 2026-07-03

### New & expanded content
* Chief AI Officer bundle (operator's manual for the AI strategy owner)
* AI Transformation Lead bundle (operator's manual for the program owner)
* AI Risk Officer bundle (operator's manual for model-level risk)
* AI Governance Lead bundle (operator's manual for AI policy operationalization)
* AI Security Lead bundle (operator's manual for model-level security)

### Site & structure
* Restructure ai-enablement under a new ai-accountability container

## v7.0.0 — AI Enablement bundle — 2026-07-02

### New bundle: AI Enablement

The operator's manual for the person accountable for AI adoption inside an organization — the **AI Enablement Lead**. A new top-level bundle, sibling to Enterprise AI Transformation (which covers the program at leadership altitude); this is the enablement seat, deep.

Eight pages:
- **What AI Enablement Is — and the Role** — the discipline, why adoption is the binding constraint, and the role/title taxonomy.
- **Who's Accountable for What** — the shared-accountability model up the chain, so you are not made accountable for adoption you cannot control.
- **Standing Up the Function** — Center of Excellence models, the AI Council, funding, and decision rights.
- **Finding Where AI Earns Its Keep**, **Building the Champion Network**, **Enablement That Sticks**, **Measuring Adoption**, and **When It Stalls** — the operator's how-to arc.

Grounded in primary sources (IBM CEO Study 2026, Microsoft AI Center of Excellence guidance), citation-audited, and dual-gated.

## v6.1.1 — 2026-07-02

## Site & structure

- Consistent navigation: each area now leads with its "start here" page (what it is / how it works), instead of that page landing wherever it fell alphabetically. Fixes, for example, the Decision Guides order so *How These Guides Work* comes before the guides.

## v6.1.0 — 2026-07-02

## New & expanded content

- **Decision Guides — When to Let AI Do It** — a new guide on whether to hand a task to AI or do it yourself: where AI earns its keep, where to keep your hands on the work, and how to decide task by task. Anchored in primary agent-guidance on when to keep a human in the loop (sensitive, irreversible, or high-stakes work).

## v6.0.0 — 2026-07-02

## New & expanded content

- **Decision Guides** — a new area of cited, plain-language guides for the recurring, consequential decisions a knowledge worker faces: the real options, the criteria that matter, the tradeoffs with sources, and when each choice wins. Built to be used with your AI assistant — connect it and your agent works from grounded, sourced criteria instead of a generic pros-and-cons list.
- **First guide: Build vs. Buy** — whether to build a capability in-house or buy it off the shelf, anchored in primary-source evidence (McKinsey–Oxford on IT-project risk, the software-maintenance cost share, and Geoffrey Moore's core-vs-context).

## v5.4.1 — 2026-07-02

## Site & structure

- Reordered the top-level navigation so Enterprise AI Transformation sits directly below What's Changed and above AI Briefs.

## v5.4.0 — 2026-07-02

## New & expanded content

- **AI Briefs — Exposed but Unprepared** — a new brief opening the **Workforce and Skills** theme in Industry Briefs. It reads an HFS Research study finding 27 million Global 2000 jobs exposed to AI over three years, and argues the real problem is how few of those companies (only 14%) have a coherent plan. The brief deliberately defuses the headline: "exposed" bundles job loss with job redesign, the figures are one firm's estimate, and the firm sells the transition it describes — while keeping the useful signal that unprepared companies are cutting hardest and hiring least.

## v5.3.2 — 2026-07-02

## Site & structure

- The homepage now speaks in the first person — Knowledgeville is written and shared by me, still linking out to One Step Labs.
- Refreshed the AI Use Cases summary to include Realtors and the new AI Playbooks, and to stay current as more sub-domains are added.

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
