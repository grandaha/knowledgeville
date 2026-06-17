---
type: Playbook
title: "Practitioner Guide: AI Incident Response"
description: AI incident taxonomy, severity tiers, response playbook, escalation paths, regulatory notification requirements, and how agentic AI changes the incident response calculus.
tags: [ai-governance, incident-response, escalation, regulatory, agentic-ai]
timestamp: "2026-06-17"
---

AI incidents increased 56.4% in 2024 — to 233 documented incidents — and then 55% again in 2025, reaching 362, per the Stanford HAI AI Index and the AI Incident Database. That trajectory is not a statistical blip. It reflects the real-world consequences of deploying systems at scale before the operational infrastructure to manage them is in place. Most organizations' existing incident response playbooks don't cover AI-specific failure modes, because most of those playbooks were written for a world of servers, software bugs, and data breaches.

This guide covers how to build an AI-specific incident response capability. It is meant for practitioners — the people who will actually receive the alert at 2 a.m. — not for executive briefings. See the [AI Governance and Risk core framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/core-framework.md) for the governance structures this playbook sits inside, and the [Acceptable Use Policy Guide](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/practitioner-guide-ai-policy-and-acceptable-use.md) for the policies that define what constitutes a violation in the first place.

---

## Why existing IR frameworks don't fit

A model producing systematically biased outputs isn't a system outage. A hallucination that gets into a customer communication isn't a data breach. An agentic AI that places 200 wrong purchase orders isn't a traditional software bug. Organizations that route these incidents through their existing IT incident process end up with three predictable problems: no clear owner, no meaningful escalation criteria, and no regulatory compliance posture.

The failure mode is structural. IT incident management is built around service availability and security integrity. AI incidents can occur while the system is fully available and completely secure — the model is just producing outputs that are wrong, harmful, or systematically discriminatory. That distinction needs to be built into your process before an incident occurs, not improvised during one.

---

## AI incident taxonomy

Six categories cover the majority of AI incidents in the wild.

**Model performance degradation.** The model's outputs become less accurate or reliable over time due to data drift, concept drift, or training data becoming stale. The system hasn't failed — it's still running, still returning predictions — but those predictions are increasingly wrong. Example: a demand forecasting model trained on pre-pandemic purchasing patterns that was never retrained performs increasingly poorly post-2022 as consumer behavior shifted. Without monitoring baselines, this category of incident goes undetected until downstream damage accumulates.

**Harmful or biased output.** The model produces outputs that discriminate, cause harm, or violate policy — discriminatory scoring, offensive content generation, or unsafe medical advice. The canonical example in this category is facial recognition systems with significantly higher error rates on darker-skinned faces deployed in high-stakes screening contexts (hiring, law enforcement, access control). The harm is in the decision, not the infrastructure.

**Hallucination and factual error at scale.** The model generates confident but false statements that propagate through downstream decisions or communications. This category matters when AI output feeds automated workflows — when a wrong answer goes to ten thousand customers, or when a hallucinated legal citation makes it into an external filing. The incident is not one wrong answer; it is the propagation path.

**Data breach via AI vector.** Sensitive data is exposed or exfiltrated through AI system behavior — prompt injection attacks, model inversion (reconstructing training data from model responses), or data leakage through API responses. The Samsung ChatGPT incident, in which employees inadvertently exposed proprietary source code and internal meeting notes by pasting them into an external AI system, is the canonical example of the third type. The data wasn't hacked; employees handed it to a third-party system without understanding the implications.

**Adversarial attack.** An actor deliberately manipulates AI inputs to produce a desired output — prompt injection for LLMs, adversarial examples for image classifiers, data poisoning attacks during training. These incidents typically have a security component and should involve the CISO from the outset. The intent to cause harm distinguishes them from performance degradation, even when the surface symptoms look similar.

**Agentic cascade failure.** An agentic AI system — one that takes sequences of actions autonomously — takes an incorrect action that cascades. The downstream effects multiply because the system continued operating after the initial error. Example: an agentic procurement tool that misidentifies a contract approval threshold and places 200 wrong purchase orders before a human catches it. The error wasn't 200 simultaneous bad decisions; it was one bad decision that the system repeated at machine speed.

---

## Severity tiers

A four-tier model (P1–P4) with response SLAs.

**P1 — Critical.** Regulatory breach, active harm to persons, data exfiltration in progress, or an agentic system causing irreversible real-world effects. Response: immediate escalation to CISO, CLO, and CAIO; system suspension within one hour; regulatory notification review within 24 hours.

**P2 — High.** Biased output that has affected a material number of decisions; hallucination that has propagated to customers or external stakeholders; a third-party vendor's AI system causing a policy violation that the organization is accountable for. Response: escalate to the AI Governance Lead and the affected business unit VP within four hours; scope assessment within 24 hours; remediation plan within 72 hours.

**P3 — Medium.** Performance degradation identified by monitoring before it causes consequential decisions; internal hallucination caught before external exposure; a policy violation by an employee using AI in a prohibited manner. Response: ticket opened with AI governance within one business day; review within five business days; root cause analysis within two weeks.

**P4 — Low.** Near-miss, policy clarification request, or a monitoring alert that investigation confirms does not represent an actual problem. Response: logged for governance review; addressed in next quarterly review cycle.

The P1/P2 line is the most consequential. Incidents that start as P3 can escalate rapidly — particularly in agentic contexts where a system has continued operating since the anomaly was first detected. Escalation criteria should be reviewed regularly and calibrated against incidents that have actually occurred.

---

## Response playbook

**Phase 1 — Detect.** AI incidents surface through several channels: model monitoring alerts (tools such as Arize Phoenix, WhyLabs, or Fiddler), user-submitted reports through internal feedback mechanisms, anomaly detection in downstream systems (a sudden spike in customer escalations, an unusual pattern in decision outcomes), or external reports from affected parties. Detection requires baseline performance metrics established at deployment time. Without baselines, "degradation" is not a measurable condition — you cannot detect drift from a reference point you never established.

**Phase 2 — Contain.** Stop the bleeding before investigating the cause. Containment actions depend on incident type: for a model producing harmful outputs, suspend the deployment or insert a mandatory human review gate; for an agentic system, revoke the agent's API credentials or restrict it to read-only mode; for a data breach via AI vector, revoke the compromised API key immediately and begin auditing what was accessed and when. Containment should happen faster than root cause analysis — the goal is to stop the incident from expanding while the investigation begins.

**Phase 3 — Assess.** Scope the incident: how many decisions or outputs were affected, who was harmed or potentially harmed, what data was involved, and what the root cause appears to be. The AI-specific wrinkle here is time horizon. Bias incidents and performance degradation incidents often require reviewing historical outputs, not just the recent window — a model that has been running for six months with degraded performance has produced six months of affected decisions. Establishing a realistic scope for P1/P2 incidents is a prerequisite for regulatory notification.

**Phase 4 — Remediate.** Fix the root cause, not just the symptom. A model producing biased outputs needs retraining on corrected data, a change to the decision pipeline, or a policy change upstream — not just an output filter that masks the bias without addressing it. An agentic cascade failure may require redesigning the checkpoints where the system must seek human confirmation before taking consequential actions. Document all remediation steps with enough specificity for regulatory review; high-level summaries are insufficient for serious incident reports.

**Phase 5 — Review.** Conduct a post-incident review within two weeks for P1 and P2 incidents. Required outputs: root cause analysis, verification that remediation is effective, changes to monitoring or policy, and a determination of whether the incident triggers regulatory reporting obligations or notification to affected persons. The review is also the mechanism for feeding findings back into governance — patterns across incidents are as important as individual root causes.

---

## Escalation paths

| Role | When they're engaged |
|---|---|
| AI Governance Lead | P2 and above; initial incident coordinator |
| CISO | Any incident with a security or adversarial component; any P1 |
| CLO / Legal | Any incident with regulatory notification implications, potential litigation, or external-facing harm |
| Communications / PR | Any P1 where external parties have been affected and public disclosure is possible |
| Regulators | Per notification requirements below |

One design principle overrides everything else here: escalation paths must be defined before an incident, not improvised during one. The governance charter should document who calls whom within one hour of a P1 declaration, including backup contacts for after-hours escalation. This is not a detail. Organizations that discover their escalation paths during a P1 incident consistently make worse decisions under time pressure than those that rehearsed them in advance.

---

## Regulatory notification requirements

This is where organizations are most often caught unprepared. AI incidents increasingly carry mandatory notification requirements, and the timelines are short.

**EU AI Act.** High-risk AI systems must notify the relevant national supervisory authority of serious incidents. A "serious incident" under the Act includes incidents causing death, serious damage to health or property, or significant adverse societal impact. Timeline: notification within 15 days for most serious incidents; the timeline is shortened for incidents involving death or suspected causation of death.

**GDPR and US state privacy laws.** If the AI incident involves personal data — even if the data was accessed by the AI model rather than exfiltrated in a traditional breach — this may trigger data breach notification requirements. GDPR requires notification to supervisory authorities within 72 hours of becoming aware of a breach affecting EU persons. US state law timelines vary (California, New York, and others have their own regimes), but 30–72 days is a common range for notification to affected individuals.

**Financial services.** The OCC, Federal Reserve, and FDIC's model risk management expectations under SR 11-7 and the updated SR 26-2 guidance apply to consequential model failures. Material model failures should be escalated through model risk governance processes and may require disclosure to bank examiners during examination cycles. AI governance programs that are not integrated with model risk management will have compliance gaps here.

**Healthcare.** HIPAA breach notification requirements apply when protected health information (PHI) is involved in an AI incident. FDA guidance on AI-enabled medical devices is still evolving; organizations with AI in diagnostic or clinical decision support contexts should maintain a direct channel to legal and compliance on any P1 or P2 incident.

**Practical rule:** engage legal on any P1 immediately; engage legal within 72 hours for any P2 incident involving personal data or regulated domains. Do not wait for legal to determine definitively that notification is required before engaging them — the clock on regulatory timelines may already be running.

---

## Agentic AI incidents: why they're different

The standard incident response calculus assumes a human receives a wrong output and decides what to do with it. Agentic AI systems break that assumption in four ways.

**Time compression.** An agentic system can take thousands of actions in the time it takes a human to receive a monitoring alert and log in to investigate. By the time the incident is detected, the damage may already be far larger than the initial trigger event.

**Reversibility.** Some agentic actions cannot be undone — sent emails, submitted forms, executed financial transactions, deleted records. Post-incident remediation for agentic systems often requires negotiating with external parties to reverse actions, not just redeploying a corrected model.

**Causal ambiguity.** "Was this an incident?" is harder to answer when the system didn't produce a single wrong output. An agentic system may have followed a plausible-seeming chain of reasoning that happened to have a bad outcome. Distinguishing an incident from normal variance in agentic behavior requires comprehensive action logs and defined outcome criteria established before deployment.

**Required IR capabilities for agentic systems.** The following are not optional for organizations deploying agentic AI in consequential contexts: complete action logs with sufficient detail to reconstruct what the agent did and why; defined checkpoints at which the agent must seek human confirmation before proceeding with high-stakes or irreversible actions; kill switches that can halt the agent without data corruption or leaving transactions in an inconsistent state; and sandbox environments for testing whether a proposed fix actually changes the agent's behavior before redeployment.

Regulatory coverage for agentic AI specifically is still developing. SR 11-7 and SR 26-2 do not explicitly address agentic systems, and the EU AI Act's coverage depends heavily on how the system is classified at deployment. Treat agentic systems as requiring elevated governance regardless of regulatory ambiguity — the operational risk profile justifies it independent of the compliance requirement.

---

## Building the capability before you need it

**Run a tabletop exercise.** Pick one AI use case currently in production. Simulate a P2 incident — biased outputs found in a batch of historical decisions. Walk your team through the playbook. Gaps in who owns what, how to scope historical impact, and whether you can actually contain the system quickly will surface within the first thirty minutes. Document the gaps; they are your pre-incident punch list.

**Establish baselines now.** You cannot detect model degradation without baseline performance metrics recorded at deployment. Most organizations with deployed models have no systematic monitoring in place. Instrumentation is not glamorous, but it is the only thing that makes detection possible. The absence of a baseline is itself a governance gap.

**Pre-approve communication templates.** Regulatory notifications, internal incident communications, and customer-facing statements should be drafted and legally reviewed before an incident. Drafting communications under P1 pressure, with counsel on the phone and a regulatory deadline running, produces mistakes that outlive the incident itself.

---

## Incident response readiness checklist

- [ ] AI incident taxonomy documented and distributed to governance, legal, and business unit owners
- [ ] P1–P4 severity criteria defined with explicit examples relevant to your deployed AI systems
- [ ] Escalation contacts documented for all tiers, including after-hours backup contacts
- [ ] Regulatory notification requirements mapped for each deployed AI system (EU AI Act applicability, GDPR exposure, financial/healthcare sector obligations)
- [ ] Baseline performance metrics established and actively monitored for every AI system in production
- [ ] Monitoring alerts configured with defined response owners (not just automated tickets without human accountability)
- [ ] Containment runbooks documented for each deployed system (how to suspend, restrict, or roll back)
- [ ] Historical output retrieval capability confirmed — can you reconstruct what the model decided for the past 90 days?
- [ ] Tabletop exercise completed in the past 12 months
- [ ] Communication templates pre-approved by legal (regulatory notification, internal announcement, customer statement)
- [ ] Agentic systems: action logs, human-confirmation checkpoints, and kill switches verified and tested
- [ ] Post-incident review process defined and assigned to a named owner

---

## Sources

- **EU AI Act** (Regulation (EU) 2024/1689), Articles 73–76: serious incident reporting obligations for high-risk AI systems. [EUR-Lex](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=OJ:L_202401689)
- **AI Incident Database (AIID)** — incident tracking database maintained by the Responsible AI Collaborative; source for incident count trends. [incidentdatabase.ai](https://incidentdatabase.ai)
- **Stanford HAI AI Index Report 2025** — source for 2024–2025 AI incident growth statistics. [aiindex.stanford.edu](https://aiindex.stanford.edu/report/)
- **NIST AI Risk Management Framework (AI RMF 1.0)** — GOVERN, MAP, MEASURE, and MANAGE functions provide the governance scaffolding within which incident response operates. [nist.gov/artificial-intelligence](https://www.nist.gov/artificial-intelligence)
- **Federal Reserve SR 11-7 / SR 26-2** — Supervisory Guidance on Model Risk Management; SR 26-2 extends coverage to AI/ML models in financial institutions.
- **GDPR Article 33** — personal data breach notification to supervisory authority (72-hour requirement). [gdpr-info.eu](https://gdpr-info.eu/art-33-gdpr/)
