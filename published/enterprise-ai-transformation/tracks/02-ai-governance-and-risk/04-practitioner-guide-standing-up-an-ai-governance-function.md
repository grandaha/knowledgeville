---
type: Playbook
title: "Practitioner Guide: Standing Up an AI Governance Function"
description: How to design, staff, and operationalize an AI governance function — org models, key roles, 90-day launch sequence, and governance structures for agentic AI.
tags: [ai-governance, org-design, policy, roles, agentic-ai]
timestamp: "2026-06-17"
---

## What this guide is for

This guide is written for the practitioner — or small team — handed the mandate to build an AI governance function, either from scratch or by rationalizing a scattered collection of existing policies, committees, and informal review processes into something coherent and defensible. You will find the conceptual framework for why governance matters and how it fits into a broader transformation effort in the [core framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md). This guide is about the operational work: what structure to adopt, who needs to own what, and what to do in the first ninety days. Policy writing (acceptable use, model cards, third-party vendor terms) and incident response design are each covered in their own guides; this one focuses on the governance function itself.

---

## The 4 governance org models

There is no single right structure for AI governance. The right model depends on your organization's size, regulatory exposure, existing risk infrastructure, and — honestly — the political will to give the governance function real authority. Four patterns account for most real-world deployments.

### 1. Centralized AI Center of Excellence

A single team owns both strategy and governance for AI across the organization. Governance is one of several mandates alongside enablement, tooling standards, and skills development.

**Pros:** Clear accountability, no coordination overhead between units, easy to build consistent standards. Works well when AI deployments are still relatively concentrated and the org is small enough that a central team can maintain visibility.

**Cons:** Doesn't scale past a certain point — the CoE becomes a bottleneck as deployment volume grows. Business units often experience it as slow or out of touch with operational realities.

**Best fit:** Organizations under roughly $1B in revenue, or enterprises where AI adoption is still early-stage and centralized visibility is achievable.  <!-- noev: organization-sizing threshold / rhetorical time-allocation figure, not a sourced statistic -->

### 2. Federated with central standards (most common in large enterprises)

A small central team sets policy, standards, and risk tiers. Business units own day-to-day compliance within those guardrails and staff their own AI champions or risk leads. The central team reviews high-risk deployments and handles cross-cutting issues (regulatory changes, incident escalations, vendor governance).

**Pros:** Scales well; business units retain operational autonomy; central function can remain small if it is well-designed. This is the dominant pattern in large regulated enterprises.

**Cons:** Requires genuine investment in the distributed layer — if business unit champions are nominal roles without time or training, the federation is fictitious. Central standards must be updated consistently or the whole system fragments.

**Best fit:** Large enterprises with multiple lines of business, especially those with significant variation in AI maturity across units.

### 3. Embedded in existing risk and compliance

AI governance is absorbed into the existing enterprise risk management or compliance function. No new structure is created; AI-specific requirements are layered onto existing frameworks (operational risk, IT risk, vendor risk).

**Pros:** Lowest cost and fastest to stand up; avoids organizational politics of creating a new function; can leverage existing audit and review infrastructure.

**Cons:** Highest risk of AI being treated as an edge case. Frameworks designed for financial or operational risk are structurally ill-suited to evaluate model behavior, training data quality, or the emergent properties of agentic systems. AI expertise rarely exists in traditional risk teams.

**Best fit:** Organizations where AI use is genuinely narrow and low-risk, or where budget constraints make a dedicated function untenable in the near term. Treat this as a transitional state, not a destination.

### 4. Board-level AI committee with operating working group

AI governance is anchored at the board level — a dedicated AI committee or expanded audit/risk committee with AI in scope. A cross-functional working group (legal, technology, ethics, business) handles operational governance under board-level oversight.

**Pros:** Signals seriousness to regulators, investors, and external stakeholders; ensures governance has organizational standing when it conflicts with business pressure; appropriate for high-stakes sectors.

**Cons:** Slow-moving for operational decisions; requires board-level education; working group can become a committee of committees without clear decision rights.

**Best fit:** Heavily regulated industries (financial services, healthcare, defense) or organizations deploying AI in genuinely high-stakes domains (credit, hiring, clinical decision support).

---

## Key roles to define

Most governance functions start with one or two people wearing multiple hats. That is fine. The goal is not a full org chart on day one — it is documented accountability so that every governance responsibility has a named owner. Here are the roles that matter, and the mistake that most commonly undermines each.

### Chief AI Officer (CAIO)

The CAIO owns the organization's AI strategy, policy, and governance at the executive level. In US federal agencies, this role is required under OMB M-24-10 (March 2024) and retained under OMB M-25-21 (April 2025), which rescinded and replaced M-24-10 while preserving the CAIO requirement. In the private sector, this is frequently an expanded scope added to the CDO or CTO rather than a net-new hire — which is pragmatic as long as the expanded mandate comes with real authority and not just a new title.

**Common mistake:** The CAIO role is staffed but has no genuine authority to block or pause AI deployments. Without decision rights, the function is advisory only and will be ignored when it conflicts with a business priority.

### AI Ethics / Responsible AI Lead

This person owns the practical application of responsible AI principles — fairness, transparency, safety, and explainability — to specific systems and deployment decisions. The role requires enough technical fluency to evaluate model behavior claims directly, not just read vendor documentation.

**Common mistake:** Hiring a policy-oriented person without the technical depth to evaluate model cards, audit results, or bias testing methodology. If your Responsible AI Lead cannot challenge a model vendor on their evaluation methodology, you have a policy writer, not a governance function.

### Model Risk Manager

Owns the organization's model risk framework: model inventory, model validation standards, and ongoing monitoring requirements. This role should be organizationally distinct from the teams that build or procure models — independence is the governance mechanism, not an org chart preference.

**Common mistake:** Putting model risk management inside the team that builds models. Validation performed by the building team is not independent validation. This is the lesson the Federal Reserve encoded in SR 11-7 for financial models; it applies equally to AI systems.

### AI Legal and Privacy Counsel

In-house or outside counsel with specific awareness of the EU AI Act (prohibited uses enforceable since February 2025, high-risk system obligations enforceable from August 2026), applicable US state AI laws (Colorado, Illinois, Texas, and others in progress), and sector-specific regulations with AI implications: HIPAA for clinical AI, FCRA for credit-related AI, EEOC guidance on AI in hiring.

**Common mistake:** Relying on general counsel with no AI-specific background to advise on AI governance decisions. General counsel will default to the most conservative reading of existing law, which may be either overly restrictive or miss AI-specific obligations entirely.

### Business Unit AI Champions

The distributed layer of a federated governance model. These are domain experts within each business unit who own day-to-day AI governance: logging new deployments, applying the risk tier framework to their use cases, and escalating edge cases to the central function.

**Common mistake:** Treating AI Champion as an honorary title rather than a role with dedicated time. Champions who spend 2% of their time on governance are not doing governance; they are providing cover for ungoverned AI.  <!-- noev: organization-sizing threshold / rhetorical time-allocation figure, not a sourced statistic -->

One important note: most organizations begin with one or two people covering the bulk of these responsibilities. That is a reasonable starting point. The discipline is in documenting who owns what — even if the answer is "same person" for multiple roles — so accountability is explicit and gaps are visible.

---

## The governance charter

A governance charter is the founding document of the AI governance function. It does not need to be long; it needs to be unambiguous on five questions.

**Scope statement.** Which AI systems, vendors, and use cases fall under this governance function? Define AI broadly enough to capture generative AI, automated decision systems, and vendor-provided AI embedded in enterprise software — not just internally-built models. If vendor AI is out of scope, write that explicitly so the gap is visible rather than invisible.

**Decision rights matrix.** Who has authority to approve AI deployment in high-risk domains? Who can block a deployment that fails a governance review? Who owns the final decision when the governance function says no and a business unit disagrees? A governance function without blocking authority is a suggestion box.

**Risk tiers.** Define what constitutes high, medium, and low risk for your organization's specific context. EU AI Act tiers are a useful reference but are not a substitute for internal risk tiering — the Act's high-risk categories are defined for regulatory enforcement, not for internal review resource allocation. A customer service chatbot may be medium-risk under EU AI Act and genuinely high-risk for your brand.

**Review cadence.** New AI deployments require a defined review process before launch. Existing systems require annual reviews as a floor, with triggered reviews on incidents, material capability changes, or significant regulatory developments (new enforcement dates, new guidance, new state laws).

**Escalation paths.** Document the escalation sequence when normal governance processes break down: business unit disagrees with governance decision, legal and technical risk assessments conflict, or a vendor refuses to provide documentation required for review. Undefined escalation paths default to whoever is most persistent.

---

## 90-day launch sequence

### Days 1–30: Inventory

Before you can govern AI, you need to know what AI exists. This is harder than it sounds — AI systems live in vendor SaaS products, in internal tools built by individual teams, in data science pipelines that were never reviewed by anyone outside the data science team, and in automated decision workflows that predate the current AI governance conversation.

Deliverables: a complete catalog of AI systems in production and in active development, mapped to business function and data type. For each system, note whether any governance review has ever occurred. Map each system to existing risk and compliance structures (vendor risk, IT risk, data privacy) to identify coverage and gaps.

### Days 31–60: Foundation

Draft the governance charter (see above) and circulate for review across legal, technology, and at least one major business unit. Establish a formal intake process for new AI deployments — even a simple intake form with a defined reviewer creates accountability that did not exist before. Identify the two or three highest-risk systems from your inventory for priority review.

Deliverables: signed governance charter, documented intake process, priority review list.

### Days 61–90: Operationalize

Run the first formal governance reviews on your priority systems. These reviews serve two purposes: they surface actual risk in the highest-stakes deployments, and they demonstrate that the governance process works — which matters for organizational credibility. Publish an acceptable use policy (see the [policy guide](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-ai-policy-and-acceptable-use.md) for specifics). Train business unit AI champions on the intake process, risk tiers, and escalation paths. Schedule the first quarterly governance review.

Deliverables: completed reviews of priority systems, published acceptable use policy, trained champions, first quarterly review on the calendar.

---

## Governing agentic AI — why it's different

Agentic AI systems — those that take sequences of actions with real-world consequences, such as sending emails, querying and modifying database records, executing code, or making API calls to external services — create governance gaps that existing model risk processes were not designed to address.

Traditional model risk management, as defined in SR 11-7 and its AI-adjacent successor SR 26-2, reviews a model at a defined point in time against a defined set of inputs and outputs. Agentic systems do not have a stable input-output relationship — their behavior evolves based on the tools they can access, the context accumulated across multi-step tasks, and the outputs of prior actions feeding into subsequent ones. A validation that shows acceptable behavior in a controlled test environment may tell you very little about behavior under real operational conditions.

The failure mode for agentic AI is also categorically different. A conventional classification model that produces a wrong answer produces a wrong answer. An agentic system with write access to production systems can amplify a bad decision at machine speed, across multiple systems, before any human reviews the output. The cascading potential is not theoretical — it is the design intent of agentic systems, which is what makes them useful and what makes ungoverned deployment dangerous.

Governance for agentic AI requires four specific controls that standard model risk frameworks do not include:

**Tool access registry.** Every agentic deployment must have an explicit, reviewed list of what systems and actions the agent can touch. Tool access should be provisioned on a least-privilege basis and reviewed on the same cadence as the deployment itself.

**Action logging with rollback capability.** Agentic systems should log every consequential action in a format that supports post-hoc audit and, where feasible, rollback. "Where feasible" is not an escape hatch — the engineering requirement for rollback capability should be part of the deployment approval criteria, not a future enhancement.

**Human escalation triggers.** Define the conditions under which the agentic system must pause and surface a decision to a human before proceeding. These triggers should be specified at deployment time, not discovered after an incident.

**Sandbox and staging review before production.** Agentic systems should be reviewed in a staging environment that replicates production tool access before any production deployment. A staging environment that does not replicate tool access is not a meaningful test of agentic behavior.

Neither SR 11-7 nor SR 26-2 explicitly addresses agentic systems. Organizations deploying agentic AI are operating in a regulatory gap. The obligation to fill that gap internally is not optional — it is the definition of responsible deployment.

---

## The most common failure modes

**Governance has authority to review but not to block.** A function that can raise concerns but cannot halt a deployment is an advisory body, not a governance function. Business units will treat it accordingly. Only 18% of organizations have an enterprise-wide council or board with the authority to make decisions on responsible AI governance ([McKinsey, 2024](#ev-mckinsey-state-of-ai-early-2024-rai-council)) — the scarce ingredient is rarely the committee; it is the committee's teeth.

**Policy exists but the people making day-to-day AI decisions don't know about it.** A governance framework that lives on an intranet page but was never operationalized through training, intake processes, or champion networks provides no actual governance.

**The charter is never updated.** The EU AI Act's enforcement timeline (prohibited uses since February 2025, high-risk system obligations from August 2026), the accumulation of US state AI laws, and new OMB guidance in the federal sector represent a genuinely dynamic regulatory environment. A governance charter written in 2024 and not updated since is not current.

**All AI systems are reviewed with the same rigor.** Applying the same full governance review to a simple keyword-based routing rule and a customer-facing generative AI system wastes the governance function's time and creates fatigue across the organization. Risk-tiered review processes are not a shortcut — they are the only way to focus review resources where they matter.

**Vendor AI is excluded from governance scope.** "We didn't build it, so it's their problem" is not a risk management position. The organizational risk from vendor AI is the same as the organizational risk from internally-built AI — the liability, reputational exposure, and regulatory accountability land on the deploying organization, not the vendor.

---

## Checklist: Is the governance function operational?

Use this to assess readiness — or to identify the gaps that need closing.

- [ ] A governance charter exists, is signed by appropriate leadership, and has been reviewed or updated in the last 12 months
- [ ] The charter includes explicit scope covering vendor AI and embedded AI in enterprise software
- [ ] A complete inventory of AI systems in production and in development exists and is maintained
- [ ] Risk tiers are defined in terms specific to the organization's context, not copied verbatim from a regulatory framework
- [ ] A formal intake process exists for new AI deployments, with a defined reviewer and documented approval criteria
- [ ] The governance function has documented authority to block or pause deployments that fail review — not just to flag concerns
- [ ] A CAIO or equivalent executive-level owner is identified with explicit AI governance accountability
- [ ] A Model Risk Manager or equivalent is identified who is organizationally independent from model development teams
- [ ] AI Legal / Privacy Counsel has been specifically briefed on EU AI Act timelines, relevant US state laws, and sector-specific regulations
- [ ] Business unit AI Champions are identified, trained, and have dedicated time for governance responsibilities
- [ ] Agentic AI deployments have tool access registries, action logging, escalation triggers, and staging review requirements as conditions of approval
- [ ] Governance reviews of existing high-risk systems are scheduled and completed at least annually
- [ ] An acceptable use policy has been published and communicated to all employees who use or procure AI
- [ ] Escalation paths are documented for contested governance decisions
- [ ] A quarterly governance review cadence is established and active

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **McKinsey — *The state of AI in early 2024: Gen AI adoption spikes and starts to generate value*, 2024.** Just 18 percent of organizations say they have an enterprise-wide council or board with the authority to make decisions involving responsible AI governance. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-2024){#ev-mckinsey-state-of-ai-early-2024-rai-council} · verified 2026-06-21 · ⚠ secondary mirror
