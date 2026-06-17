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

> **Only 43%** of organizations have a formal AI governance policy in place *(IAPP AI Governance Survey, 2025)*
> **66%** of directors report having "limited to no knowledge or experience" with AI *(Corporate Compliance Insights, 2025)*
> **42%** of companies abandoned most of their AI initiatives in 2025 — up from 17% in 2024 *(McKinsey)*
> **13%** of organizations have already reported an AI model breach; 97% lack proper AI access controls *(IBM, 2025)*

The gap between deployment pace and governance infrastructure is where risk accumulates. Every week an organization deploys AI without standing policy, defined accountability, and a monitoring function, it adds to a liability balance that will eventually be paid — through regulatory fines, reputational damage, litigation, or forced remediation of systems already in production.

## The regulatory floor has arrived

The EU AI Act entered into force in August 2024. Prohibited AI practices became enforceable in February 2025, with fines up to €35 million or 7% of global annual revenue. Full obligations for high-risk AI systems apply from August 2, 2026. In financial services, AI-related regulatory fines surged over 150% in 2024, with U.S. regulators issuing more than $4.3 billion in total financial penalties that year. Regulators in the US, UK, and EU are converging on a common expectation: organizations must demonstrate that they know what AI systems they are running, what risks those systems carry, and who is accountable when something goes wrong. "We are still figuring out our governance" is not a defense that mitigates a fine.

## Four governance imperatives every enterprise needs

**Model risk management.** AI systems produce outputs at scale. When those outputs are wrong — biased, hallucinated, inconsistently calibrated — the damage is proportional to deployment breadth, not bounded by a single bad decision. LLM hallucinations alone cost businesses an estimated $67 billion in degraded performance in 2024 *(IBM)*. Model risk management means inventorying deployed models, defining acceptable performance thresholds, monitoring for drift, and establishing processes for intervention or shutdown.

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
- Put AI governance on the board agenda with a reporting cadence. The 40% of companies that have done this outperform peers by nearly 11 percentage points in return on equity *(MIT, 2025)*.

The rest of this track operationalizes each point: the [Core Framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/core-framework.md) establishes the risk taxonomy and accountability model, the [Assessment](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/assessment-governance-maturity-scoring.md) turns that into a scored maturity diagnostic, and three practitioner guides cover standing up the governance function, acceptable use policy, and incident response. Leaders building the AI strategy that this governance layer must support should also see [Track 01](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/index.md).

---

**Sources:** IAPP AI Governance Profession Report 2025; Corporate Compliance Insights / Deloitte Board AI Survey 2025; McKinsey State of AI 2025; IBM Security 2025; EU AI Act (Regulation (EU) 2024/1689); Fenergo Global Financial Penalties Report 2025; MIT Sloan Management Review AI-Savvy Boards Study 2025.

*Last updated: June 2026 · One Step Labs*
