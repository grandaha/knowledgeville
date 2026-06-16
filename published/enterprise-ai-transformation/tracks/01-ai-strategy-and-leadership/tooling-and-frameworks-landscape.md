---
type: Reference
title: Tooling & Frameworks Landscape
description: A survey of the strategy and maturity frameworks, roadmapping and portfolio tools, board communication tools, and ROI modeling tools used to direct enterprise AI — most general-purpose, applied to AI.
tags: [ai-strategy, tooling, frameworks, roadmapping, roi]
timestamp: "2026-06-15"
---

## How to Use This Landscape

This is a survey of the frameworks and tools that support the work of this track — setting an AI strategy, prioritizing a portfolio, building a roadmap, communicating it to the board, and making the investment case. Pair it with the three working pages it supports: [the core framework](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/core-framework.md) (what a good strategy contains), [the practitioner guide](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/practitioner-guide-running-an-ai-strategy-process.md) (how to run the strategy process), and [the strategic readiness assessment](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/assessment-strategic-readiness-scoring.md) (how to score where you stand).

One honest caveat up front: there is very little AI-*strategy*-specific tooling. The frameworks below are general strategy and maturity models applied to AI, and the tools are general product-management, business-intelligence, and cloud-finance platforms used for AI portfolios and spend. Choose for fit and for what you already run — not for an "AI" label on the box.

---

## Strategy & Maturity Frameworks

The named models leaders use to set AI strategy, prioritize investments, and benchmark organizational readiness. These are methodologies and assessment models rather than software, most published by major consultancies and analysts; many can be self-applied or used through the originator's advisory engagement.

| Framework | What it is / when to use | Originator |
|---|---|---|
| **Rewired / "Rewiring for AI"** | A maturity and transformation model arguing that AI value comes from organizational "rewiring" (strategy, talent, operating model, technology, data, adoption) rather than algorithms alone; paired with the recurring *State of AI* "AI high performers" research. Use to diagnose why pilots stall and what high performers do differently. | McKinsey & Company ([rewiring-for-ai](https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/rewiring-for-ai-from-ambition-to-advantage)) |
| **10-20-70 principle** | A resource-allocation heuristic: ~10% of AI effort on algorithms, 20% on technology and data, and 70% on people and process change. Use when setting transformation budgets and where to weight change management. | Boston Consulting Group (BCG) |
| **AI Maturity Model** | A five-stage progression — Awareness, Active, Operational, Systemic, Transformational — for benchmarking where an organization sits on its AI journey. Use for a structured maturity self-assessment and target-state planning. | Gartner ([AI Maturity Model toolkit](https://www.gartner.com/en/chief-information-officer/research/ai-maturity-model-toolkit)) |
| **Value-vs-feasibility prioritization** | A 2×2 approach scoring AI use cases on business value against implementation feasibility, supported by Gartner's industry "Use-Case Prisms." Use to build and rationalize an AI use-case portfolio and roadmap. | Gartner ([For AI Value, Focus on Your Use Cases](https://www.gartner.com/en/articles/ai-value)) |
| **Three Horizons of Growth** | A portfolio model staging initiatives across Horizon 1 (defend the core), Horizon 2 (emerging growth), and Horizon 3 (future options); applied to balance near-term AI deployment against longer-term bets. Use to set growth ambition and allocate investment across time. | McKinsey & Company (*The Alchemy of Growth*, 1999) |
| **AI Readiness Index** | A periodic benchmarking survey scoring readiness across six pillars (Strategy, Infrastructure, Data, Governance, Talent, Culture) and segmenting firms into Pacesetters, Chasers, Followers, and Laggards. Use to benchmark readiness against external peer data. | Cisco ([AI Readiness Index](https://www.cisco.com/c/m/en_us/solutions/ai/readiness-index.html)) |

---

## AI Roadmapping & Portfolio Tools

There is no dominant AI-strategy-specific roadmapping product. In practice, leaders manage AI roadmaps and initiative portfolios in general-purpose product, roadmap, and project/portfolio management (PPM) tools, applying standard prioritization scoring to AI use cases.

| Tool | What it does | Best for |
|------|--------------|----------|
| **Aha!** | Product roadmapping and strategy suite linking goals and initiatives to releases; supports custom scorecards for prioritization. | Leaders wanting strategy-to-delivery traceability and structured scoring across a portfolio. |
| **Productboard** | Product management platform for capturing inputs, prioritizing features, and building roadmaps; supports custom prioritization scoring. | Teams prioritizing a backlog of AI ideas against value and effort. |
| **Jira Product Discovery** | Atlassian idea-prioritization and roadmapping tool with custom fields, calculated RICE scores, and an impact-vs-effort view; connects ideas to Jira delivery tickets. | Atlassian-based orgs wanting prioritization plus a path to delivery tracking. |
| **airfocus** | Modular prioritization and roadmap platform supporting RICE, weighted scoring, and collaborative "Priority Poker" sessions. | Leaders who want flexible, framework-driven scoring of AI initiatives. |
| **Tempo Strategic Roadmaps** (formerly Roadmunk) | Roadmap visualization and prioritization tool offering timeline and swimlane roadmaps with a built-in prioritization matrix. | Communicating an AI roadmap to executive and stakeholder audiences. |
| **Monday.com** | Configurable work/portfolio management platform with boards, dashboards, and status tracking. | Tracking the status, owners, and progress of active AI projects. |
| **Asana** | Work management platform with portfolios, goals, and custom fields for cross-initiative reporting. | Operational tracking and reporting across concurrent AI initiatives. |

Most of these support custom scoring fields, so the value-vs-feasibility and weighted-scoring methods from [the practitioner guide](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/practitioner-guide-running-an-ai-strategy-process.md) can be implemented directly — score each initiative on business value and feasibility, then plot it to surface quick wins versus longer-term bets.

---

## Board & Executive Communication Tools

What leaders use to report AI strategy, progress, and risk to boards and the C-suite. Most are general executive-communication tools, not AI-specific; their relevance comes from how the AI program is framed within them. The communication *artifacts* below matter more than any single product.

**Software (general-purpose, repurposed for AI program reporting)**

| Tool | What it's for |
|------|---------------|
| Diligent Boards | Board portal for securely distributing board books, materials, and minutes to directors; also offers GRC/risk modules. |
| Nasdaq Boardvantage | Board portal for meeting management and secure document sharing with directors. |
| Microsoft Power BI | BI/dashboard platform used to build executive dashboards, including AI program KPIs and adoption metrics. |
| Tableau (Salesforce) | BI/visualization tool used to create executive-facing dashboards and scorecards. |
| PowerPoint / Google Slides | Presentation tools used for board decks and strategy walkthroughs. |

Board portals (Diligent, Boardvantage) distribute materials and run meetings; BI tools (Power BI, Tableau) supply the underlying metrics. None is purpose-built for AI.

**Communication artifacts and frameworks (practices, not products)**

- **One-page AI strategy** — a single page summarizing ambition, priority use cases, investment, and expected outcomes, used to align the board and C-suite on direction.
- **OKRs (Objectives and Key Results)** — a goal-setting practice that ties AI initiatives to measurable outcomes and cascades them from executive to team level.
- **Board-level AI dashboard** — a curated set of indicators (adoption, value delivered, spend, model and data risk, incidents) presented at recurring board or committee meetings; assembled in BI tools or slides rather than bought off the shelf.
- **Balanced scorecard** — a strategy framework (Kaplan and Norton) covering financial, customer, internal-process, and learning perspectives, sometimes adapted to track AI initiatives across those dimensions.

---

## Investment Case & ROI Modeling Tools

ROI and investment-case work for AI is rarely done in a single dedicated product. In practice it combines a spreadsheet-based financial model, a value framework, and cloud or FinOps tooling to model and track the underlying spend. Expect to assemble these rather than buy one tool that does all three.

**Methods and frameworks (the analytical core)**

- **Spreadsheet TCO/ROI model** — Excel or Google Sheets remains the default. Models capture total cost of ownership (compute/inference, licensing, data, integration, MLOps, and change-management/headcount costs) against quantified benefits. This is honestly where most AI business cases live.
- **NPV, IRR, and payback-period analysis** — standard capital-budgeting techniques applied to the investment's cash flows to test whether projected value justifies the spend over time.
- **Value-pool / value-driver analysis** — top-down framing (popularized by McKinsey and BCG) that sizes addressable value — cost takeout, revenue uplift, productivity — by function or process before attributing it to specific initiatives.
- **Benefit attribution and baselining** — establishing a pre-AI baseline and tracking measured deltas, so claimed ROI can be defended after deployment rather than only forecast.

**Tools for modeling and tracking AI spend**

| Tool / Framework | What it's for | Best for |
|---|---|---|
| AWS Cost Explorer / Budgets | Visualize, forecast, and alert on AWS spend including AI/ML and Bedrock usage | Modeling and tracking AI workloads on AWS |
| Microsoft Cost Management (Azure) | Analyze and budget Azure and Azure OpenAI consumption | Azure-centric AI estates |
| Google Cloud Billing / Cost reports | Monitor and forecast GCP and Vertex AI spend | Google Cloud AI workloads |
| Apptio Cloudability (now IBM Apptio) | Multi-cloud cost visibility, allocation, and TCO/showback analysis | Enterprises needing cross-cloud cost allocation |
| FinOps Foundation framework (incl. FOCUS spec) | Vendor-neutral practice and standard for cloud cost accountability, increasingly extended to "FinOps for AI" | Operationalizing ongoing AI cost governance |

Cloud cost tools track and forecast *spend*, not business value. Quantifying benefits and computing ROI still depends on the spreadsheet model plus a value framework above. The measurement and attribution discipline itself lives in [Track 08, Measurement & Value Realization](/enterprise-ai-transformation/tracks/08-measurement-and-value-realization/index.md).

---

## References

- McKinsey & Company — *Rewired: A McKinsey Guide to Outcompeting in the Age of Digital and AI* / *Rewiring for AI* and the *State of AI* research
- Boston Consulting Group — *Where's the Value in AI?* (the 10-20-70 principle)
- Gartner — *AI Maturity Model* and *For AI Value, Focus on Your Use Cases*
- McKinsey & Company — *The Alchemy of Growth* (Three Horizons of Growth), 1999
- Cisco — *AI Readiness Index*
- Kaplan & Norton — *The Balanced Scorecard*
- FinOps Foundation — *FinOps Framework* and the *FOCUS* cloud-cost specification
