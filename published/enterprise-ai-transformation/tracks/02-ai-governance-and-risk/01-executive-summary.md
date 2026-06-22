---
type: Concept
title: Executive Summary
description: A one-page synthesis of AI Governance & Risk — for board members and senior leaders deciding whether to fund a governance program.
tags: [ai-governance, risk, compliance, executive-summary]
timestamp: "2026-06-16"
---

*A one-page synthesis of the AI Governance & Risk knowledge base — for board members and senior leaders deciding whether to fund a governance program.*

---

AI governance is no longer an IT control. It is a board-level risk management function — and most enterprises are running it three to four years behind where their AI deployments already are.

> **Only 43%** of organizations have a formal AI governance policy in place ([PEX Network, 2025](#ev-pex-network-2025-ai-governance-policy))
> **66%** of directors report having "limited to no knowledge or experience" with AI ([Deloitte, 2025](#ev-deloitte-governance-ai-2025-board-knowledge-gap))
> **42%** of companies are abandoning most of their AI initiatives — up from **17%** a year earlier ([S&P Global Market Intelligence, 2025](#ev-sp-global-vote-2025-abandoned-ai-initiatives))
> **13%** of organizations have already reported an AI model breach — and **97%** of those lacked proper AI access controls ([IBM, 2025](#ev-ibm-2025-ai-breaches-controls))

The gap between deployment pace and governance infrastructure is where risk accumulates. Every week an organization deploys AI without standing policy, defined accountability, and a monitoring function, it adds to a liability balance that will eventually be paid — through regulatory fines, reputational damage, litigation, or forced remediation of systems already in production.

## The regulatory floor has arrived

The EU AI Act entered into force in August 2024. Prohibited AI practices became enforceable in February 2025, with fines up to €35 million or 7% of global annual turnover ([EU AI Act, 2024](#ev-eu-ai-act-2024-article-99-penalties)). Full obligations for high-risk AI systems apply from August 2, 2026 ([European Commission, 2024](#ev-ec-ai-act-2024-application-timeline)). Financial regulators are already enforcing aggressively in adjacent compliance domains — U.S. regulators issued more than $4.3 billion in financial-crime penalties in 2024 ([Fenergo, 2024](#ev-fenergo-financial-penalties-2024-us-regulators)) — signaling the enforcement posture AI deployments will face. Regulators in the US, UK, and EU are converging on a common expectation: organizations must demonstrate that they know what AI systems they are running, what risks those systems carry, and who is accountable when something goes wrong. "We are still figuring out our governance" is not a defense that mitigates a fine.

## Four governance imperatives every enterprise needs

**Model risk management.** AI systems produce outputs at scale. When those outputs are wrong — biased, hallucinated, inconsistently calibrated — the damage is proportional to deployment breadth, not bounded by a single bad decision. Model risk management means inventorying deployed models, defining acceptable performance thresholds, monitoring for drift, and establishing processes for intervention or shutdown.

**Vendor and third-party AI risk.** Most enterprise AI runs on components the organization did not build: foundation models, APIs, embedded AI in SaaS products, and AI-enabled services from supply chain partners. Terms around training data, data retention, model updates, and output licensing change without announcement. Third-party AI risk management is the extension of existing vendor risk processes to cover these AI-specific exposures — and it is materially different from standard vendor due diligence.

**Regulatory compliance.** The EU AI Act is the most structurally significant regulation, but it is not the only one. Sector-specific rules in financial services (model risk management guidance from the OCC, FRB, and FDIC), healthcare, and hiring are already in force or imminent. Organizations with global operations face overlapping requirements. Compliance requires mapping each AI deployment to the applicable regulatory category, documenting how it meets requirements, and maintaining that documentation as models and regulations evolve.

**Internal policy and acceptable use.** Without a published acceptable use policy, employees resolve ambiguity individually — which means the same risks get taken inconsistently and without organizational awareness. An acceptable use policy defines what AI tools employees may use, what data may be input into which systems, who approves new use cases, and what happens when an incident occurs. It is the governance layer closest to actual daily risk.

## What "not governed" looks like versus "governed"

Without governance, AI systems accumulate in business units with no central inventory, vendor contracts are signed without AI-specific risk review, the first time leadership learns about a model failure is from a news article or a regulator, and acceptable use is whatever individual employees decide on the day. With governance, there is a maintained inventory of all AI deployments mapped to risk tiers, vendor AI terms are reviewed against policy before signature, incidents surface through internal channels first and trigger a documented response, and employees have clear guidance and a path to escalate uncertainty.

The difference is not primarily one of resources. Organizations that established governance early spent significantly less than organizations that are now retrofitting it onto systems already in production.

## What leadership should take from this

- Establish or formally charter an AI governance function — even a lightweight one — before the August 2026 EU AI Act high-risk deadline. Most enterprises are still in the gap between "working on it" and "formally accountable."
- Conduct an AI system inventory now. You cannot govern, monitor, or report on systems you do not know exist.
- Extend vendor due diligence to cover AI-specific terms: training data provenance, data retention, model update notification, output liability, and right to audit.
- Publish an acceptable use policy. It is the single highest-leverage low-cost governance action available, and most organizations do not have one.
- Put AI governance on the board agenda with a reporting cadence. Companies with AI-savvy boards — about a quarter of firms — averaged roughly 11 percentage points higher return on equity than their industry peers ([MIT Sloan Management Review, 2025](#ev-mitsmr-cisr-2025-ai-savvy-boards-roe)).

The rest of this track operationalizes each point: the [AI Governance Framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md) establishes the risk taxonomy and accountability model, the [Assessment](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/05-assessment-governance-maturity-scoring.md) turns that into a scored maturity diagnostic, and three practitioner guides cover standing up the governance function, acceptable use policy, and incident response. Leaders building the AI strategy that this governance layer must support should also see [AI Strategy & Leadership](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/index.md).

---

*Last updated: June 2026 · One Step Labs*

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **PEX Network — *PEX Report 2025/26 (Global State of Process Excellence)*, 2025.** Just 43 percent of surveyed organizations have an AI governance policy, with 25 percent still implementing one and 29 percent having none. [View source](https://www.processexcellencenetwork.com/business-transformation/reports/pex-report-global-state-process-excellence){#ev-pex-network-2025-ai-governance-policy} · verified 2026-06-21 · primary
- **Deloitte Global — *Governance of AI: A critical imperative for today's boards (2nd edition)*, 2025.** While two-thirds of respondents (66%) say their boards still have 'limited to no knowledge or experience' with AI, this number is an improvement over the 79% in the previous survey. [View source](https://www.deloitte.com/global/en/issues/trust/progress-on-ai-in-the-boardroom-but-room-to-accelerate.html){#ev-deloitte-governance-ai-2025-board-knowledge-gap} · verified 2026-06-21 · primary
- **S&P Global Market Intelligence — *Generative AI shows rapid growth but yields mixed results (Voice of the Enterprise: AI & Machine Learning, Use Cases)*, 2025.** The proportion of companies that abandon most of their AI initiatives has increased from 17% to 42%, with the average organization scrapping 46% of its proof-of-concept projects prior to production. [View source](https://www.spglobal.com/market-intelligence/en/news-insights/research/2025/10/generative-ai-shows-rapid-growth-but-yields-mixed-results){#ev-sp-global-vote-2025-abandoned-ai-initiatives} · verified 2026-06-21 · ⚠ secondary mirror
- **IBM (Ponemon Institute) — *Cost of a Data Breach Report 2025*, 2025.** 13% of organizations reported breaches of AI models or applications, 97% of which reported lacking proper AI access controls. [View source](https://newsroom.ibm.com/2025-07-30-ibm-report-13-of-organizations-reported-breaches-of-ai-models-or-applications,-97-of-which-reported-lacking-proper-ai-access-controls){#ev-ibm-2025-ai-breaches-controls} · verified 2026-06-20 · primary
- **European Union — *Regulation (EU) 2024/1689 (AI Act), Article 99*, 2024.** administrative fines of up to 35 000 000 EUR or up to 7% of total worldwide annual turnover (whichever is higher) for prohibited practices; up to 15 000 000 EUR or 3% for breaches of operator obligations (Articles 16, 26 and others); up to 7 500 000 EUR or 1% for incorrect or misleading information. [View source](https://artificialintelligenceact.eu/article/99/){#ev-eu-ai-act-2024-article-99-penalties} · verified 2026-06-21 · primary
- **European Commission — *Regulatory framework on AI (Regulation (EU) 2024/1689)*, 2024.** the governance rules and the obligations for general-purpose AI models became applicable on 2 August 2025; the majority of remaining obligations, including rules for high-risk AI systems, apply from 2 August 2026. [View source](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai){#ev-ec-ai-act-2024-application-timeline} · verified 2026-06-21 · primary
- **Fenergo — *Financial-crime / AML enforcement penalties study (full-year 2024)*, 2024.** In 2024, U.S. regulators issued over $4.3 billion in fines, with North America accounting for 95% of the $4.6 billion in global financial penalties. [View source](https://resources.fenergo.com/newsroom/fenergo-study-regulatory-penalties-in-north-america-account-for-95-of-global-financial-penalties-in-2024){#ev-fenergo-financial-penalties-2024-us-regulators} · verified 2026-06-21 · primary
- **MIT Sloan Management Review / MIT CISR — *AI-Savvy Boards Drive Superior Performance*, 2025.** Companies with digitally and AI-savvy boards averaged 10.9 percentage points above industry average in return on equity; only 26% of companies clear the bar for 'digitally and AI savvy' boards. [View source](https://sloanreview.mit.edu/article/ai-savvy-boards-drive-superior-performance/){#ev-mitsmr-cisr-2025-ai-savvy-boards-roe} · verified 2026-06-21 · primary
