---
type: Playbook
title: "Assessment: Governance Maturity Scoring"
description: A six-dimension diagnostic that scores the maturity of an organization's AI governance function — structure, policy, model risk, regulatory readiness, incident response, and vendor risk.
tags: [ai-governance, assessment, maturity, compliance, model-risk]
timestamp: "2026-06-16"
---

## What This Is For

This assessment scores one thing: whether the **governance function** is mature enough to oversee the AI the organization has already deployed — or is actively building. It is not a compliance checklist and it is not a strategy audit. Those live in [the core governance framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/core-framework.md) and [Track 01's strategic readiness assessment](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/assessment-strategic-readiness-scoring.md). This one measures whether the oversight apparatus — the structure that catches problems before they become liabilities, the policies that constrain misuse, the mechanisms that detect incidents — is real and operational, versus nominal and aspirational.

It is the diagnostic companion to [standing up an AI governance function](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/practitioner-guide-standing-up-an-ai-governance-function.md) and [AI policy and acceptable use](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/practitioner-guide-ai-policy-and-acceptable-use.md). Run it to identify the weakest link before deploying AI in consequential domains.

> While **80% of large organizations claim active AI governance initiatives**, fewer than half can demonstrate measurable governance maturity *(Gartner, 2024)*
>
> Only **25% of organizations have fully implemented AI governance programs** despite **93% using AI in some capacity** — a deployment-to-oversight gap of nearly 70 percentage points *(AuditBoard, 2025)*

This framework produces a prioritized gap list, not a score to report upward. If the result doesn't change what gets funded, what gets enforced, or what gets escalated in the next 90 days, the assessment wasn't worth running.

---

## The Six Dimensions

Score each dimension on a 1–5 scale, independently, on evidence rather than intent. The dimensions don't average into a grade so much as combine into a shape — and the shape tells you where to invest first.

### Dimension 1: Governance Structure and Mandate

This dimension measures whether a formal AI governance function exists with explicit authority, named accountable owners, and a mandate that is enforced rather than advisory. Governance without structure is opinion. The question is not whether the organization has talked about AI governance but whether someone is accountable for it and empowered to act on that accountability.

| Level | What it looks like |
| --- | --- |
| 1 | No governance structure. AI decisions are made ad hoc by technical teams or business units; no one is named as accountable for AI risk. |
| 2 | A nominal owner is identified (often a title added to an existing role), but the mandate is undefined, the authority is informal, and no cross-functional coordination exists. |
| 3 | A governance body exists (committee, council, or function) with a written charter naming members and scope; it meets on a cadence, but its decisions are advisory and can be ignored without consequence. |
| 4 | A formal governance function has documented decision rights, a budget, and the authority to halt or condition AI deployments; decisions are binding, with an escalation path to the board. |
| 5 | AI governance is fully embedded in enterprise risk governance; the function operates autonomously, reports to the board, integrates with audit, legal, and compliance, and continuously updates its mandate as the risk landscape evolves. |

Evidence to collect: governance charter with named members and decision rights, organizational chart showing reporting line, budget line for governance activities, evidence of a decision being enforced (deployment blocked or conditioned), board-level reporting artifact.

---

### Dimension 2: Policy Coverage and Enforcement

This dimension assesses whether an AI acceptable use policy (AUP) exists, whether it is comprehensive enough to cover the actual uses occurring, and — critically — whether it is enforced. A policy that no one reads and nothing enforces is not governance; it is documentation theater. Coverage and enforcement are scored together because a narrowly scoped policy with strong enforcement is more protective than a comprehensive policy with no enforcement mechanism.

| Level | What it looks like |
| --- | --- |
| 1 | No AI policy exists. AI use is governed only by general IT acceptable use policy, if that. |
| 2 | A basic AI policy exists on paper but has no named owner, no review date, no employee acknowledgment mechanism, and no enforcement process. |
| 3 | A documented AUP with a named owner, last-reviewed date, and employee acknowledgment log exists; it defines permitted and prohibited uses, but enforcement is complaint-driven and reactive. |
| 4 | The AUP is actively enforced: prohibited uses are technically blocked where feasible, training completion is tracked, violations are documented, and policy review is scheduled on a defined cycle with substantive updates. |
| 5 | Policy coverage extends to all material AI use (internal builds, vendor-supplied tools, embedded AI in SaaS); enforcement is proactive; exceptions require documented approval; the policy is updated when new use cases, tools, or regulations emerge. |

Evidence to collect: AUP document with named owner, dated review, and acknowledgment log; documented prohibited use categories; technical controls blocking prohibited uses (e.g., DLP rules, approved-tools list); violation log; exception-approval records; evidence of policy update triggered by a new use case or regulation.

---

### Dimension 3: Model Risk Management

This dimension assesses whether production AI models are inventoried, monitored, versioned, and reviewed for performance, bias, and drift. An AI model deployed to production and then left unmanaged is a liability that grows over time: data distributions shift, model behavior degrades, biases that were not present at launch emerge. Model risk management is the operational discipline that catches these failures before they cause harm or become regulatory exposure.

| Level | What it looks like |
| --- | --- |
| 1 | No model inventory exists. The organization cannot enumerate the AI models in production; no monitoring is in place. |
| 2 | An informal list of major models exists but is not maintained; some monitoring is in place for performance, but there is no systematic bias review, no version control on model updates, and no defined review cadence. |
| 3 | A formal model registry catalogs production models with owners, use cases, risk classification, and deployment dates; basic performance and drift monitoring runs, but bias review and adversarial testing are ad hoc. |
| 4 | All production models are registered, version-controlled, and subject to a defined review cycle; performance, drift, and fairness metrics are monitored continuously; model updates require a documented approval before deployment. |
| 5 | Model risk management is fully embedded in the deployment pipeline: automated drift detection triggers reviews, bias audits are scheduled, high-risk models are subject to human-in-the-loop requirements, and model retirement has a governed decommission process. |

Evidence to collect: model registry with entries for each production model including owner, risk tier, and review date; monitoring dashboards with drift and performance metrics; documented bias assessment for at least one production model; version history and approval records for a recent model update; decommission record for a retired model.

---

### Dimension 4: Regulatory Readiness

This dimension measures whether the organization understands which regulations apply to its AI systems and what those regulations require — not just broadly ("AI Act exists") but specifically ("these three of our systems are high-risk under Article 6, here is the compliance gap, and here is the remediation plan"). Regulatory readiness is not compliance; it is knowing what compliance requires. Organizations that discover their obligations only when an audit or enforcement action begins have no runway to close gaps.

| Level | What it looks like |
| --- | --- |
| 1 | No regulatory mapping exists. The organization has not assessed which AI regulations apply and has not assigned responsibility for tracking them. |
| 2 | The legal or compliance team has general awareness of applicable regulations (e.g., EU AI Act, sector-specific rules) but has not mapped specific obligations to specific systems; compliance responsibility is unclear. |
| 3 | A regulatory inventory maps known applicable regulations to AI use cases; a named owner tracks regulatory developments, but the gap between current state and compliance is not formally assessed. |
| 4 | A documented regulatory gap assessment covers all material AI systems; each gap has an owner and a remediation timeline; the organization can demonstrate what it would need to show a regulator for its highest-risk systems. |
| 5 | Regulatory readiness is continuous: horizon scanning identifies new obligations before enforcement, systems are classified and updated as regulations evolve, and the organization participates in industry bodies shaping AI regulation. |

Evidence to collect: regulatory inventory mapping regulations to specific AI systems; classification of systems by risk tier (e.g., under EU AI Act Article 6); documented gap assessment for at least one regulated system; remediation plan with named owners and dates; evidence of regulatory horizon scanning (newsletter, counsel memo, or working-group membership).

---

### Dimension 5: Incident Detection and Response

This dimension assesses whether the organization can detect, classify, and respond to AI-specific incidents — model failures, bias events, data poisoning, output manipulation, unauthorized use — and whether it has defined what an AI incident is in the first place. Security incident response is necessary but insufficient: AI incidents have characteristics (gradual model drift, latent bias, adversarial prompting) that general cybersecurity playbooks do not cover. Without a defined AI incident taxonomy and tested response procedures, the organization is flying blind.

| Level | What it looks like |
| --- | --- |
| 1 | No AI incident taxonomy or response process exists. AI failures are discovered by users or customers; there is no mechanism to detect, classify, or escalate them. |
| 2 | AI failures are handled ad hoc through general IT or security escalation paths; there is no defined AI incident category, no named AI incident responder, and no documented response procedure. |
| 3 | An AI incident taxonomy is defined (distinguishing, for example, model failure, bias event, security compromise, and misuse); a response procedure document exists; a named owner is assigned; but the procedure has not been tested. |
| 4 | AI incident response procedures are tested (tabletop or live drill); detection mechanisms exist for major incident categories; incidents are logged and reviewed post-resolution; lessons learned feed governance updates. |
| 5 | Continuous monitoring detects AI incidents automatically; classification is automated for common incident types; response SLAs are defined and tracked; the incident log informs model risk reviews, policy updates, and regulatory reporting; external reporting obligations are met on time. |

Evidence to collect: AI incident taxonomy document; written response procedure with named owner; dated drill or tabletop exercise record; incident log with at least one closed entry; post-incident review and lessons-learned record; evidence that an incident finding changed a policy or model configuration.

---

### Dimension 6: Vendor and Third-Party AI Risk

This dimension assesses whether AI systems delivered by third parties — SaaS vendors with embedded AI, API-accessed foundation models, AI-powered analytics platforms — are governed with the same rigor as internally built systems. Vendor AI is often the least-governed AI in the enterprise: it arrives through procurement channels rather than engineering processes, and its model behavior, training data, and output risks are largely opaque to the buyer. Yet liability for harm from vendor AI sits with the deploying organization, not the vendor.

| Level | What it looks like |
| --- | --- |
| 1 | No vendor AI governance exists. Third-party AI tools are procured and deployed with no assessment of model risk, data handling, or contractual accountability. |
| 2 | Procurement reviews exist for major software vendors, but AI-specific questions (model behavior, training data, bias testing, incident notification) are not asked; vendor AI is not inventoried separately. |
| 3 | A vendor AI inventory exists; standard AI-specific due-diligence questions are included in the procurement checklist; high-risk vendors are identified, but contractual protections and ongoing monitoring are inconsistent. |
| 4 | All material vendor AI systems are inventoried and risk-tiered; contracts include AI-specific terms (audit rights, incident notification, model change notification, data-use restrictions); high-risk vendors are subject to periodic reassessment. |
| 5 | Vendor AI governance is fully integrated with enterprise AI governance: vendor models are included in the model registry, third-party incidents trigger internal incident response, and vendor AI use is subject to the same acceptable-use policy as internal AI. |

Evidence to collect: vendor AI inventory listing each third-party AI system with risk tier; procurement checklist showing AI-specific due-diligence questions; at least one contract with AI-specific terms (incident notification clause, model change notice requirement, or data-use restriction); record of a vendor reassessment; evidence that a vendor AI system is included in the internal model registry or monitoring program.

---

## The Five Maturity Levels

Average the six dimensions for a single maturity level — but treat the average as a label, not the finding. The lowest dimension matters more than the mean.

| Level | Name | Where you are |
| --- | --- | --- |
| 1 | Nascent | No governance infrastructure. AI is deployed ad hoc, ungoverned, and unmonitored. Risk accumulates silently. |
| 2 | Developing | Governance exists on paper — a nominal owner, a draft policy, a rough vendor list — but nothing is enforced, tested, or maintained. The documentation gives a false sense of coverage. |
| 3 | Emerging | Structure, policy, and basic model oversight are in place; the governance function is real but not yet operational at scale. Processes exist but are inconsistently applied and untested under pressure. This is where most organizations sit, and where they stall. |
| 4 | Scaling | Governance is operational and enforced across the material AI portfolio; incidents are detectable; vendor risk is managed; regulatory obligations are mapped and actively closed. |
| 5 | Transformational | Governance is continuous, automated where appropriate, and embedded in all AI delivery processes — procurement, deployment, monitoring, and retirement. The function proactively shapes how the organization uses AI rather than reviewing it after the fact. |

The gap between Level 3 and Level 4 is where most programs stall. The jump from documented processes to operational enforcement requires dedicated capacity (someone whose job is governance, not governance as a 10% time commitment), technical controls that make compliance the path of least resistance, and an escalation mechanism that is actually used. Without those, a Level 3 organization will keep producing governance artifacts that do not govern.

---

## How Governance Maturity Gates the Other Tracks

Governance is not a parallel track — it is the constraint that determines whether the other seven tracks can be trusted. A low governance score means risk is accumulating in every other track, often invisibly.

- **Models deployed without risk management create compounding liability.** Every production model without monitoring (Track 04, AI Platform & MLOps) is accumulating drift, bias risk, and unexplained behavior. The later governance is imposed, the more expensive the remediation — and the more exposure the organization has carried in the interim.
- **Ungoverned vendor AI creates compliance exposure that surfaces at the worst time.** Most organizations have more AI embedded in SaaS tools than they have built internally. When a regulatory audit or incident triggers scrutiny, discovering that vendor AI contracts contain no audit rights or incident notification terms — after the fact — is a crisis that a Level 4 vendor governance program would have prevented.
- **Adoption without policy creates legal and HR exposure.** Without an enforced acceptable-use policy, Track 06 (Adoption & Change Management) is spreading AI use without the guardrails that protect both employees and the organization. Employees experimenting with AI tools in the absence of clear guidance will, predictably, make choices that expose confidential data or violate third-party terms.
- **Weak governance blocks regulated industries from scaling.** For organizations in financial services, healthcare, or any sector covered by high-risk categories under the EU AI Act or comparable frameworks, governance maturity is not a nice-to-have — it is the gate. A Level 2 governance score means scaling in regulated domains is not yet permissible; the investment in Tracks 03–05 has no viable path to production.

---

## How to Run the Assessment

**Assemble the right group.** No single function can score all six dimensions honestly. You need general counsel or a compliance lead, the CISO or head of information security, the AI or data team lead, at least one business-unit leader who owns a deployed AI system, and — if it exists — the governance function owner. Without legal and security in the room, policy and regulatory dimensions will be systematically over-scored. The session should run 90 minutes.

**Score on evidence, not intent.** For each dimension, rate 1–5 and capture the evidence that supports it — the specific artifacts named in each "Evidence to collect" line. Not "we have a policy" but "here is the AUP document with its named owner, its last-reviewed date, and the acknowledgment log." A score inflated by optimism produces a roadmap built on fiction.

**Read the lowest dimension as the binding constraint.** One dimension almost always limits governance effectiveness regardless of strength elsewhere. A Level 4 policy program with a Level 1 model registry means risk is accumulating in production that the policy was never designed to catch. The binding constraint is what to fix first.

**Act on the shape within 90 days.** For the lowest-scoring dimensions, commit to concrete, owned, measurable actions completable in the next quarter. The assessment is only valuable if it changes what gets funded and assigned in the next 90 days. If it produces a slide and a meeting note, it was not worth running.

---

## Scoring Template

Use this in your assessment session:

| Dimension | Score (1–5) | Supporting evidence | Key gap | 90-day action |
| --- | --- | --- | --- | --- |
| Governance Structure and Mandate | | | | |
| Policy Coverage and Enforcement | | | | |
| Model Risk Management | | | | |
| Regulatory Readiness | | | | |
| Incident Detection and Response | | | | |
| Vendor and Third-Party AI Risk | | | | |
| **Average** | | | | |

**Interpreting the average:**

- **1.0–2.0:** Governance is not functional. Do not scale AI deployment — expose and close the structural gaps before expanding any AI program.
- **2.0–3.0:** Governance infrastructure exists but is not operational. Identify the binding constraint and fix it before funding downstream AI work in regulated or high-risk domains.
- **3.0–4.0:** Governance is real but incomplete. Build systematically toward enforcement and operational testing; raise the lowest dimension first.
- **4.0–5.0:** Governance is operational. Focus on automation, continuous improvement, and integration with enterprise risk management.

---

## What to Do With the Results

The most common failure mode: the assessment produces a score, someone presents it in a leadership review, and it is filed. The score is not the output — the constraint identification and the 90-day actions are. If the lowest-scoring dimension does not have a named owner and a funded workstream within two weeks of the session, the assessment will not change anything.

**Use the results to gate downstream investment, not just to plan governance work.** If this assessment reveals a Level 1 or 2 model risk management program, the right decision may be to pause new AI deployments in high-risk domains until the monitoring infrastructure is in place. Governance maturity is a prerequisite for responsible scaling, not an activity that runs in parallel with it. Presenting the results to the executive team as "governance needs investment" without the funding implication spelled out — "we are not able to safely deploy AI in domain X until this is resolved" — is a soft message that will not drive resource allocation.

**Governance maturity typically surfaces ownership gaps that were invisible before.** When an organization runs this assessment and discovers a Level 2 vendor risk program, the usual finding is not that the problem was unknown — it is that no one owned it. Legal assumed procurement handled it; procurement assumed IT handled it; IT assumed legal handled it. The assessment forces a conversation about who actually owns each dimension. Those ownership assignments, made explicit and committed to in writing, are often the most durable output of the exercise.

**Feed the lowest-scoring dimensions into the governance council agenda.** Whatever steering body owns AI governance — whether a formal AI risk committee or a combined technology and risk council — the lowest-scoring dimensions should be standing agenda items until they reach Level 3 or above, with a named owner presenting progress at each meeting. A governance body that does not track its own maturity has no mechanism to improve. The re-score date — typically 90 days after the initial assessment — should be on the calendar before the session ends.

---

## Sources

- AuditBoard — *State of Audit, Risk, and Compliance: AI Edition* — 2025
- Gartner — *AI Governance Survey: Measuring Maturity Across Large Organizations* — 2024
- IAPP — *AI Governance Profession Report* — 2025
- CSA and Google Cloud — *Cloud AI Governance and Security Study: Governance Maturity Is the Strongest Predictor of AI Readiness* — 2025
- Ncontracts — *State of Third-Party Risk Management Survey* — 2025
