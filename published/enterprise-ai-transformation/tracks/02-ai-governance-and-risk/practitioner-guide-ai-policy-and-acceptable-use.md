---
type: Playbook
title: "Practitioner Guide: AI Policy and Acceptable Use"
description: How to write and maintain an AI acceptable use policy — risk tiering, prohibited and permitted use categories, human-in-the-loop requirements, data classification, and EU AI Act alignment.
tags: [ai-governance, policy, acceptable-use, human-in-the-loop, eu-ai-act]
timestamp: "2026-06-17"
---

## What this guide is for

Most organizations have an "AI policy." A significant number of those policies are either so abstract that no one can apply them to a concrete decision, or a laundry list of prohibitions that no one enforced because no one owned them. This guide is for the person who has been handed the task of writing or substantially rewriting that policy — turning it into something business units can actually follow and that the governance function can audit and enforce.

A useful acceptable use policy (AUP) is not a legal document sealed in amber. It is an operational document that defines how the organization uses AI tools, what requires oversight, what is off-limits, and who is responsible for what. It needs to be specific enough to drive decisions, flexible enough to outlast the current generation of tools, and owned by someone who will maintain it.

Before writing the AUP, ground yourself in the governance structure it will live inside. The [AI Governance and Risk core framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/core-framework.md) describes how policy fits into the broader governance architecture. If your organization does not yet have a governance function to own and enforce the policy, start with [Standing Up the AI Governance Function](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/practitioner-guide-standing-up-an-ai-governance-function.md) — a policy without an owner and an enforcement mechanism is shelf-ware from the moment it is published.

---

## Start with risk tiers, not a list of rules

The most common structural mistake in AI policy writing is leading with a list of specific tools or systems — approved tools here, prohibited tools there. This approach has one fatal flaw: the tool landscape changes faster than any policy review cycle. A list that was current in January is outdated by June.

A risk-tiered policy defines criteria and lets reviewers apply those criteria to new tools, new use cases, and new capabilities as they emerge. The policy ages much better because the underlying question — how consequential is this use, and for whom? — is durable even when the tooling is not.

The following four-tier model is a practical starting point. The exact boundaries between tiers are organizational judgment calls, and you should adjust them to match your industry, regulatory environment, and risk appetite. What matters is that the tiers are explicit, documented, and defensible — not that they match this template exactly.

**Tier 1 — Prohibited**
Uses that are banned outright, regardless of what safeguards are claimed. Examples include: covert surveillance of employees via AI-powered monitoring without their knowledge; discriminatory scoring of individuals for hiring, lending, or housing without human review; AI-generated impersonation of real, identifiable individuals (deepfakes for deception); real-time biometric identification in public spaces (prohibited under the EU AI Act); and social scoring systems that aggregate behavioral data to assign trust or eligibility scores. These uses are not subject to an exception process — they are not permitted.

**Tier 2 — High-Risk / Requires Approval**
Uses in consequential domains that require formal review and sign-off before deployment. Examples include: AI systems that inform or support HR decisions (hiring, performance evaluation, termination); clinical decision support tools; credit-scoring or loan underwriting systems; law enforcement applications; content moderation at scale; and any system that determines whether a person is eligible for a service, benefit, or opportunity. The defining characteristic is that an error causes material harm to a person.

**Tier 3 — Standard Use / Requires Guardrails**
General productivity and content uses that are permitted with documented safeguards. Examples include: AI writing assistance for external-facing content (with human review before publication), customer-facing chatbots, AI-generated summaries of meeting transcripts, and code generation for production systems. Guardrails include output review requirements, data handling restrictions, and disclosure obligations where applicable.

**Tier 4 — Open Use**
Low-risk uses with minimal oversight requirements. Examples include: internal brainstorming, summarization of non-sensitive internal documents, code assistance for non-production or prototype code, and personal productivity tools used on non-sensitive work. These uses carry minimal harm potential and do not warrant formal approval or mandatory review processes.

---

## AUP structure: the seven components

An acceptable use policy needs the following seven components to be operationally useful rather than ceremonially complete.

**1. Scope**
Define who and what the policy covers. At minimum: all employees and contractors, any vendor or partner using organization-provided AI tools, and any AI tool that touches organization data — regardless of whether the tool was procured formally or brought in informally (shadow AI). Scope creep is a real risk; err toward broad coverage with a carve-out process rather than a narrow definition that leaves obvious gaps.

**2. Risk tier definitions and examples**
Reproduce the tier definitions here with organization-specific examples drawn from use cases your business units actually encounter. Abstract definitions are harder to apply than examples employees recognize. If your organization runs clinical trials, a Tier 2 example should reference clinical data. If you are a financial services firm, a Tier 2 example should reference credit decisions. Generic examples produce generic application.

**3. Approval process for Tier 2 deployments**
Specify who reviews Tier 2 deployments, what documentation is required for submission, and how long the review process takes. Ambiguity here is where the policy breaks down in practice — if business units cannot find out who to ask or how long to wait, they will skip the process. The approval workflow should include: a submission template (use case description, data inputs/outputs, affected populations, technical safeguards), a named review committee or role, an SLA (e.g., 15 business days for standard review), and a path for expedited review when the business timeline is constrained.

**4. Prohibited use list (Tier 1 specifics)**
Name the categories explicitly. Do not rely on "illegal uses" or "uses that violate applicable law" — that formulation sounds comprehensive but provides no operational guidance. Name the categories: covert employee surveillance, discriminatory eligibility scoring, impersonation, real-time biometric identification in public spaces, emotion recognition in employment or education contexts. If your organization operates in the EU, the EU AI Act's prohibited use list (Article 5) should be reflected here verbatim.

**5. Data handling rules**
Specify what data can be sent to external AI services and what cannot. This is where most organizations have the largest gap. At minimum, the policy should address: personal data (PII) and its regulatory treatment, regulated data categories (HIPAA protected health information, FCRA-covered credit data, ITAR/export-controlled technical data), trade secrets and proprietary information, and attorney-client privileged communications. The policy should state which data categories are prohibited from being submitted to which class of AI service — external API (data leaves the organization), organization-hosted cloud service (data stays in tenant), or on-premise deployment (data never leaves controlled infrastructure). This is not a theoretical risk. In 2023, Samsung engineers pasted proprietary source code into ChatGPT on multiple occasions; that data became part of OpenAI's training pipeline. The incident cost Samsung significant internal remediation and produced a near-total ban on external AI tool use — an outcome that a clear data handling policy could have prevented.

**6. Disclosure and transparency requirements**
Specify when users must be told they are interacting with AI and when AI-generated content must be labeled as such. Customer-facing chatbots should identify themselves as AI in most jurisdictions; some states have enacted explicit disclosure requirements. AI-generated content submitted as original work (in vendor proposals, regulatory filings, published research) presents different disclosure questions. The policy should distinguish between disclosure to external parties (customers, regulators, the public) and internal transparency requirements (labeling AI-generated content in internal documents).

**7. Enforcement and exceptions**
What happens when someone violates the policy? The policy should specify the escalation path and the range of consequences, which in most organizations will align to the existing HR disciplinary framework. Equally important is the exception process: if a use case does not fit neatly into a tier, or if a business unit has a compelling reason to operate outside the standard rules, how do they request an exception? Who approves it? How is it documented? An exception process that works will reduce pressure on business units to operate outside the policy quietly.

---

## Human-in-the-loop requirements

Human oversight of AI systems is not binary. It exists on a spectrum, and policy language that requires "human review" without specifying what kind creates ambiguity that erodes in practice.

The three oversight modes are:

- **Human-in-the-loop (HITL):** A human must actively review and approve the AI output before any action is taken. The AI does not act autonomously.
- **Human-on-the-loop (HOTL):** The AI can act, but a human receives notification, can monitor outputs, and can intervene to override or correct. Suitable for use cases where the cost of occasional errors is acceptable and real-time intervention is feasible.
- **Human-out-of-the-loop (HOOTL):** Fully automated. Appropriate only where the stakes are low, the error rate is known and acceptable, and the harm from an error is reversible.

Policy should specify which tier requires which oversight mode. A reasonable default mapping: Tier 2 uses require HITL or at minimum HOTL with a documented intervention protocol; Tier 3 uses require HOTL for consequential outputs and may permit HOOTL for low-stakes automation; Tier 4 uses permit HOOTL.

Two additional considerations should be written into the policy explicitly:

**The consequential output rule.** Any AI output that triggers a decision affecting an individual person — affecting their employment, credit access, healthcare, legal standing, or access to services — requires at minimum HOTL oversight. Fully consequential decisions (employment terminations, loan denials, clinical treatment decisions) require HITL.

**The scale consideration.** A single AI classification is not a decision. A system that automatically acts on 10,000 classifications per day is a decision-making system at scale. Volume changes the risk profile. Policy should account for this — a use case that seems low-stakes in isolation may require proportionally more oversight when it operates at scale.

The EU AI Act (Article 14) mandates that high-risk AI systems include human oversight mechanisms that allow operators to monitor, intervene, and override system outputs. Where organizations are building or deploying high-risk systems, this requirement should be treated as the floor for HITL design, not a ceiling.

---

## Data classification for AI use

The key question for any AI use case is straightforward: what data goes in, and where does it go? Policy that does not answer this question leaves the most consequential compliance risk unaddressed.

Common data categories requiring explicit policy treatment:

**Personal data / PII.** GDPR, CCPA, and an expanding body of state privacy law regulate how personal data is processed. Sending PII to an external AI service constitutes data processing under GDPR and requires a lawful basis and, typically, a Data Processing Agreement with the service provider. Policy should prohibit sending personal data to external AI services without confirmed contractual coverage and a documented lawful basis.

**Regulated data.** HIPAA protected health information, FCRA-covered consumer credit data, and ITAR/EAR export-controlled technical data each carry subject-matter restrictions that are independent of general privacy law. Policy should prohibit sending regulated data to external AI services absent specific legal review and authorization, and should specify the review process for internal or vendor-hosted deployments.

**Trade secrets and proprietary information.** The Samsung incident is the canonical example, but the risk is not limited to model training. Any data submitted to an external API may be logged, retained, or reviewed by the provider for safety, abuse detection, or product improvement purposes — depending on the provider's terms of service. Policy should require employees to confirm that data submitted to external AI services does not include trade secrets, unpublished product plans, acquisition-sensitive information, or other proprietary content before submission.

**Attorney-client privileged communications.** AI tools that process communications between lawyers and clients may implicate privilege doctrine. Policy should require legal review before any AI tool is used to process, summarize, or analyze legal communications, and should treat this category as Tier 2 at minimum.

---

## EU AI Act alignment

The EU AI Act is the most consequential AI-specific regulatory framework currently in force. Even for organizations headquartered outside the EU, the Act applies to any AI system whose output is used within the EU — the territorial scope mirrors the GDPR's effects-based approach. Non-EU organizations with EU customers, employees, or partners cannot treat EU AI Act compliance as someone else's problem.

Key alignment points for the AUP:

- **Prohibited uses (Article 5)** took effect February 2, 2025. These include: AI-based social scoring by public authorities, real-time remote biometric identification in public spaces (with narrow law enforcement exceptions), subliminal manipulation techniques, and exploitation of vulnerabilities of specific groups. These should be explicitly listed in Tier 1.
- **General-purpose AI (GPAI) obligations** (Articles 51–56) took effect August 2, 2025. These apply to providers of foundation models, not typically to enterprise users — but organizations building applications on top of GPAI models should understand the downstream documentation and transparency obligations.
- **High-risk system requirements** (Annex III) take full effect August 2, 2026. High-risk categories include: biometric identification and categorization, management of critical infrastructure, education and vocational training, employment and worker management, access to essential private services (credit, insurance), law enforcement, migration and border management, and administration of justice. Systems in these categories require conformity assessments, technical documentation, human oversight mechanisms, and in some cases registration in the EU database before deployment.

The AUP should be reviewed against the EU AI Act's enforcement timeline at each annual review cycle and updated to reflect each milestone.

---

## What makes a policy work versus what makes it shelf-ware

Signs of shelf-ware: written at a reading level that requires a lawyer to parse; no concrete examples; no approval mechanism with named owners and SLAs; no enforcement consequences; no review date. A policy with these characteristics will be clicked through during onboarding and ignored afterward.

Signs of a working policy: tier examples use real use cases that employees in your organization recognize; the Tier 2 approval process has a named owner, a submission template, and an SLA; violations have a documented escalation path; exceptions are possible and the process is clear; the policy has a published review date and a named owner who is accountable for updates.

One practical technique that significantly improves compliance: write a one-page summary of each tier for the employees who will actually use AI tools. Most employees do not need to read the full policy — they need to know whether their specific use case is open, requires a guardrail, requires approval, or is off-limits. A one-page reference card per tier, written in plain language with use-case examples, will produce more consistent behavior than a twenty-page policy document.

**Update cadence.** Review the full policy at least annually. Trigger an out-of-cycle review when any of the following occur: a new EU AI Act enforcement milestone takes effect, a significant incident occurs internally or at a peer organization, a major new AI capability is introduced (for example, first agentic deployment in a consequential domain), or a new state AI law takes effect in a jurisdiction where the organization operates.

---

## Checklist: Is the policy operational?

Use this checklist to evaluate whether a draft or existing policy is ready to function operationally:

- [ ] The scope statement covers employees, contractors, and vendors — not just "employees"
- [ ] Each risk tier has at least three concrete examples drawn from the organization's own use cases
- [ ] Tier 1 prohibitions name specific use categories, not just "illegal uses"
- [ ] Tier 2 approval process names a specific owner or committee, not a role title
- [ ] Tier 2 approval process has an SLA published alongside the policy
- [ ] Data handling rules address external APIs, hosted cloud, and on-premise separately
- [ ] The Samsung-style risk (submitting proprietary data to external AI) is explicitly covered
- [ ] HITL requirements specify the oversight mode (in-loop, on-loop, out-of-loop) not just "human review"
- [ ] EU AI Act prohibited uses (effective February 2025) are reflected in Tier 1
- [ ] Disclosure requirements address both external (customer-facing) and internal contexts
- [ ] An exception process exists, with a named approver and a documentation requirement
- [ ] The policy has a named owner, a review date, and a distribution list for updates

---

## Sources

1. **EU AI Act (Regulation (EU) 2024/1689)** — [EUR-Lex full text](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX%3A32024R1689). The definitive source for prohibited use categories, high-risk system definitions, human oversight requirements, and enforcement timelines.

2. **NIST AI Risk Management Framework (AI RMF 1.0)** — [NIST AI RMF](https://airc.nist.gov/RMF). The GOVERN, MAP, MEASURE, and MANAGE functions provide the structural backbone for operationalizing risk tiering and human oversight policy in enterprise contexts.

3. **IAPP AI Governance in Practice Report** — [IAPP Resource Center](https://iapp.org/resources/article/ai-governance-in-practice-report/). Annual survey data on how organizations are structuring AI governance, policy, and oversight functions; useful for benchmarking tier structures and approval workflows.

4. **OECD AI Principles** — [oecd.ai/en/ai-principles](https://oecd.ai/en/ai-principles). Foundational framework for transparency, human oversight, and accountability that underpins both the EU AI Act and NIST AI RMF; useful for understanding the normative basis for HITL requirements.

5. **FTC Guidance on AI and Algorithms** — [FTC Business Guidance](https://www.ftc.gov/business-guidance/blog/2023/02/keep-your-ai-claims-in-check). FTC enforcement posture on deceptive and unfair AI practices; relevant to disclosure requirements and consequential decision-making policy in US contexts.

6. **UK ICO Guidance on AI and Data Protection** — [ICO AI Guidance](https://ico.org.uk/for-organisations/guide-to-data-protection/key-dp-themes/guidance-on-ai-and-data-protection/). Practical guidance on how data protection obligations intersect with AI development and deployment; particularly useful for data classification policy where GDPR-adjacent obligations apply.
