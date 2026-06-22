---
type: Concept
title: AI Governance Framework
description: Model risk, vendor risk, regulatory compliance, and the internal policy layer that governs AI deployment.
tags: [ai-governance, risk, compliance, model-risk, eu-ai-act]
timestamp: "2026-06-16"
---

## Why AI Governance Is Different

Traditional IT governance was built to manage systems: servers, applications, databases, networks. The questions it asks are operational — is the system available, secure, and performing as designed? Governance succeeds when the system behaves as specified.

AI governance must ask a different set of questions. A model behaves as specified and still causes harm. A system performs accurately on average and still discriminates against a protected class in a specific segment. A vendor delivers the contracted output and still exposes training data in ways no contract anticipated. The specification itself can be subtly wrong, and no monitoring alert fires when it is.

This is not a marginal difference. It is a structural one. AI systems have emergent behaviors that are not derivable from their training procedures. They degrade silently as the world changes around them. They inherit the biases and limitations of the data they learned from. And they are increasingly assembled from third-party components whose behavior the deploying enterprise does not control and may not fully understand.

> **Only 25%** of organizations have a fully implemented AI governance program, despite widespread awareness of regulatory obligations ([AuditBoard, 2025](#ev-auditboard-blueprint-to-reality-2025-governance-gap))
> The average cost of a data breach reached **$4.88 million** in 2024 — its largest yearly jump since the pandemic ([IBM, 2024](#ev-ibm-cost-of-breach-2024-average-cost))

The governance gap is the management problem of the moment. AI adoption is accelerating — McKinsey's 2025 State of AI found that 88% of organizations are using AI in at least one business function ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-adoption)), up from 78% the prior year ([McKinsey, 2024](#ev-mckinsey-state-of-ai-2024-adoption)). But governance maturity has not kept pace: only about one-third of organizations report maturity levels of three or higher in strategy, governance, and agentic AI governance ([McKinsey, 2026](#ev-mckinsey-trust-2026-maturity-level-three)).

This track builds the coverage that closes that gap. It sits immediately downstream of [AI Strategy & Leadership](/enterprise-ai-transformation/tracks/01-ai-strategy-and-leadership/index.md), which sets intent and risk appetite. This track operationalizes both — converting appetite into controls, policy into enforcement, and regulatory obligation into organizational action. The [practitioner guide to standing up an AI governance function](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-standing-up-an-ai-governance-function.md) is the companion for organizations building this capability from scratch.

---

## Model Risk Management

Model risk is the risk that an AI system produces outputs that are incorrect, biased, unstable, or harmful — and that the enterprise relies on those outputs without recognizing the problem. It exists regardless of regulatory requirement. A loan decision model that drifts, a medical imaging classifier that underperforms on a demographic not well-represented in training data, a customer-facing chatbot that hallucinates at a meaningful rate: each represents model risk realized.

The financial services sector developed the most rigorous published framework for managing this risk. The Federal Reserve's SR 11-7 guidance, issued in 2011, established a three-lines-of-defense structure: model developers who build and document, independent validators who challenge assumptions and test performance, and internal audit who oversees the whole process. Originally focused on credit and market risk models, SR 11-7 now applies with full force to AI and machine learning systems. Regulators have been explicit: the most common examiner finding in 2024–2026 is that an institution's model risk policy does not reference AI or foundation models, meaning the AI tools are operating entirely outside formal model risk governance. In April 2026 the Federal Reserve, OCC, and FDIC jointly issued SR 26-2, which supersedes SR 11-7 and modernizes the framework for the AI era — but the core logic of independent validation, performance monitoring, and documented approval has not changed.

The components of a mature AI model risk program, whether or not your industry is regulated under SR 11-7:

**Model inventory and classification.** Every AI model in production — including third-party models accessed via API — is catalogued. Each entry captures what the model does, what decisions or outputs it influences, who owns it, what data it was trained on, and its risk tier (the risk to the organization if it fails). Without an inventory, governance is fictional.

**Pre-deployment validation.** Before a model goes into production, an independent reviewer (not the team that built it) assesses: accuracy and performance metrics across relevant subgroups, bias testing for legally sensitive characteristics, explainability — can the output be explained to the person it affects, and is that required? — and adversarial robustness (how does the model behave when inputs are unusual or adversarial?).

**Performance monitoring and drift detection.** Models trained on historical data will degrade as the world changes. Input drift (the data the model receives in production looks different from what it was trained on) and concept drift (the underlying relationships the model learned no longer hold) are both routine. Neither triggers an alert in the absence of deliberate monitoring. Production monitoring must track output distributions, confidence scores, and where possible, ground-truth feedback loops.

**Hallucination and reliability controls.** Generative AI adds a new class of model risk not covered by traditional frameworks: factual hallucination. A large language model presents incorrect information with high confidence, and the downstream user — or the downstream automated process — acts on it. Controls include output validation pipelines, uncertainty quantification, retrieval-augmented grounding where applicable, and human review gates for high-stakes outputs.

**Model versioning and change management.** A model updated by a vendor without notice is a governance event, even if the vendor views it as routine maintenance. Every model update must be treated as a change: re-validated, re-approved for production use, and documented. This applies to internally developed models and to third-party models accessed via API.

**Approval gates.** High-risk models — those affecting credit decisions, employment, medical outcomes, or other consequential determinations — require formal approval before deployment and re-approval after material changes. The approval record documents who validated, what was found, what conditions were imposed, and who gave sign-off.

---

## Vendor and Third-Party AI Risk

The majority of enterprise AI is now assembled from third-party components. Enterprises access foundation models from OpenAI, Anthropic, Google, and others via API. They procure AI-enabled SaaS products — HR platforms, underwriting tools, fraud detection systems — without always knowing what models are embedded in them or how those models behave. They run AI in cloud infrastructure managed by hyperscalers under shared-responsibility models that frequently leave governance accountability ambiguous.

> **49%** of financial institutions experienced a vendor-related cyber incident in the past year ([Ncontracts, 2025](#ev-ncontracts-tprm-survey-2025-vendor-cyber-incident))
> **73%** of organizations have two or fewer full-time employees managing vendor risk, even though more than half oversee more than 300 vendors ([Ncontracts, 2025](#ev-ncontracts-tprm-survey-2025-vendor-risk-staffing))

The core problem: standard vendor risk management frameworks were not designed for AI. A standard SaaS vendor risk questionnaire asks about data encryption, access controls, and disaster recovery. It does not ask whether the vendor's model was trained on data that included the customer's confidential information, whether the vendor's model can be updated unilaterally and without notice, what happens to user data submitted in prompts, or what protections exist against model outputs that discriminate against protected classes.

What an adequate AI vendor risk framework requires:

**Data handling audit.** Where does data submitted to the vendor's AI go? Is it used for model training? Is it retained, and for how long? Who can access it? For most AI API providers, the default answer to "is my data used for training?" is no — but enterprises should verify this contractually, not assume it.

**Contractual protections specific to AI.** Standard vendor contracts lack the provisions AI requires: the right to be notified of material model changes, the right to audit model behavior (or receive third-party attestation of it), SLAs expressed in terms of model output quality (not just uptime), liability allocation for AI-generated errors or discriminatory outputs, and data deletion rights that cover training data, not just data at rest.

**Model change notification rights.** A vendor updating a foundation model is a governance event for every downstream deployer. AI vendor contracts should require advance notice of material model changes, define what "material" means (changed output distributions, new capabilities, changed safety behaviors), and give the enterprise the right to re-evaluate before the change takes effect in their environment.

**AI in the supply chain.** Third-party AI risk is not limited to direct AI vendors. A supplier who uses AI in their own processes — for quality control, logistics, contracting — creates downstream risk. Due diligence for critical suppliers should now ask whether and how they use AI in processes that affect the relationship.

**AI vendor risk questionnaire.** Maintain a standard AI-specific vendor risk questionnaire (separate from general IT security questionnaires) covering: model training data sources and governance, bias and fairness testing practices, explainability and audit trail capabilities, incident response procedures for model failures, regulatory compliance attestations, and the vendor's own model change management practices.

---

## Regulatory Compliance

The regulatory environment for enterprise AI is in active construction. The EU AI Act is now the most comprehensive binding regulation, with sector-specific rules in financial services, healthcare, and other domains adding compliance obligations on top.

### EU AI Act

The EU AI Act entered into force on 1 August 2024 ([European Commission, 2024](#ev-ec-ai-act-2024-application-timeline)). It establishes a risk-tiered framework:

| Risk tier | Definition | Key requirements | Enforcement date |
|---|---|---|---|
| **Unacceptable** | AI practices prohibited outright — social scoring by public authorities, real-time biometric surveillance in public spaces, subliminal manipulation, exploitation of vulnerabilities | Complete ban | 2 February 2025 |
| **High** | AI in consequential domains: employment screening, credit scoring, healthcare access, education, law enforcement, migration/border control, critical infrastructure | Risk management system, data governance, technical documentation, transparency, human oversight, accuracy and robustness standards, registration in EU database | 2 August 2026 (standalone systems) / 2 December 2027 (Annex III embedded) |
| **Limited** | AI interacting with humans (chatbots, deepfakes) | Transparency obligations — users must know they are interacting with AI | 2 August 2026 |
| **Minimal** | AI-enabled games, spam filters, most recommendation systems | No specific obligations | N/A |

Penalties for non-compliance are substantial: up to **€35 million or 7% of global annual turnover** for prohibited AI practices, and up to **€15 million or 3%** for breaches of most other operator obligations — including the core high-risk provider and deployer duties ([EU AI Act, 2024](#ev-eu-ai-act-2024-article-99-penalties)). The higher of the fixed amount or the percentage applies.

The Act covers any organization deploying AI that affects individuals in the EU — not just EU-headquartered organizations. Global enterprises with European customers, employees, or operations are in scope. For organizations with high-risk AI systems (employment screening tools, credit decisioning, healthcare AI), compliance preparation should already be underway.

The Act also introduced General-Purpose AI (GPAI) obligations — transparency requirements for foundation model providers — effective August 2, 2025.

### Sector-Specific Rules

**Financial services — NYDFS.** In October 2024, the New York State Department of Financial Services issued guidance on AI-related cybersecurity risks for covered entities. The guidance clarifies that AI risks (including AI-enabled social engineering, adversarial attacks, and third-party AI exposure) fall within existing cybersecurity regulations and expects covered entities to conduct AI risk assessments, address AI in third-party risk programs, and maintain training programs covering AI-specific threats. The NYDFS also issued Insurance Circular Letter No. 7 (2024) in July 2024 covering AI use in insurance underwriting and pricing, requiring insurers to demonstrate that AI-driven underwriting decisions are not unfairly discriminatory.

**Healthcare — ONC/CMS.** The Office of the National Coordinator for Health Information Technology and the Centers for Medicare and Medicaid Services have issued guidance and rulemaking requiring transparency and risk management for AI decision support tools used in clinical and administrative healthcare settings. AI tools that meet the definition of a "clinical decision support" software function under the 21st Century Cures Act may require FDA oversight; those that influence coverage or payment decisions face CMS scrutiny.

**Cross-sector — FTC.** The Federal Trade Commission has signaled active enforcement against AI practices it deems unfair, deceptive, or anti-competitive — including AI-generated deceptive content, discriminatory AI in consumer decisions, and misleading claims about AI capabilities. FTC authority applies across sectors.

**ISO 42001.** Published in December 2023, ISO/IEC 42001 is the first international standard for AI Management Systems (AIMS). It applies to any organization that develops, provides, or uses AI, regardless of size or sector, covering the full AI lifecycle from design through decommissioning. Certification is voluntary but increasingly expected by enterprise procurement and by regulators in some jurisdictions as evidence of AI governance maturity. It follows the same high-level structure as ISO 27001 (information security) and ISO 9001 (quality), making it tractable for organizations with existing management system programs.

---

## The Internal Policy Layer

External regulations define the floor. The internal policy layer defines how the organization behaves above it — and for most enterprises, the internal policy layer is where AI governance either lives or dies.

A minimum-viable AI policy framework contains:

**Acceptable use policy.** Which AI tools and systems are approved for use? Who approves new AI tools (a sanctioned list, an approval process, or both)? What uses of AI are prohibited — e.g., using AI to generate legal advice provided to clients without attorney review, using AI to make final hiring decisions, using AI with personally identifiable information in unapproved tools? The acceptable use policy must be specific. "Use AI responsibly" is not a policy.

**Human-in-the-loop requirements.** For each consequential AI use case, the policy specifies whether a human must review outputs before action is taken, what that review must consist of, and what documentation is required. Automated approval of loan applications, automated rejection of job applications, automated clinical recommendations: each must have a defined human review step with an accountable owner.

**Prohibited uses.** The set of uses that are categorically off the table — not just unapproved but prohibited. Examples: using AI to surveil employees without disclosure, using AI to generate content designed to deceive about its AI origin, using AI systems not approved through the vendor risk process for any purpose involving customer data.

**Escalation paths.** When a model produces an unexpected or concerning output, who does the employee call? When a vendor notifies of a model change, who is responsible for evaluating its implications? When a potential bias incident is identified, what is the notification chain? Escalation paths are the connective tissue between front-line AI users and the governance function — and they are almost universally missing in early-stage programs.

**AI change management.** Changes to AI systems in production — new models, updated models, new use cases for existing models, new data sources — are governed by a defined process analogous to IT change management. Changes are classified by risk, assessed against the model risk framework, approved by appropriate authorities, and documented.

**Incident response.** A defined procedure for AI-related incidents: what constitutes an AI incident, how it is reported, who investigates, how it is documented, and when external disclosure (to regulators, affected individuals, or the public) is required. See the companion [AI incident response guide](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-ai-incident-response.md).

The [AI policy and acceptable use practitioner guide](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-ai-policy-and-acceptable-use.md) provides worked examples and drafting templates for each of these elements.

---

## Governance Structures and Roles

AI governance is not self-executing. Someone owns it, someone funds it, and someone is accountable when it fails. The organizational design question — who, where, and how — is among the most consequential decisions in standing up an AI governance function.

> **26%** of large enterprises now have a dedicated Chief AI Officer (CAIO), up from **11%** two years ago ([IBM Institute for Business Value, 2025](#ev-ibm-caio-study-2025-caio-adoption))
> Only **28%** of organizations report that their CEO takes direct responsibility for AI governance; only **17%** say their board of directors does ([McKinsey, 2025](#ev-mckinsey-rewiring-2025-ceo-oversight))

Four organizational models dominate in practice:

| Model | Description | Best when |
|---|---|---|
| **Centralized** | A dedicated AI governance function (team, office, or center of excellence) owns policy, validation, risk assessment, and compliance centrally | AI is used in high-risk domains; regulatory exposure is significant; consistency and control are the priority |
| **Federated** | Business units own AI governance within their domains; a central function sets standards and provides oversight but does not run the process | Scale and speed matter; business units have very different AI use cases; central capacity is constrained |
| **Committee** | A cross-functional committee (legal, compliance, risk, IT, business) exercises governance collectively; no dedicated team | AI footprint is early-stage; the organization prefers distributed accountability; dedicated headcount is not yet justified |
| **Embedded** | Governance is built into business unit processes — model risk officers embedded in business lines, compliance embedded in delivery teams | AI is deeply embedded in operations; real-time governance decisions need to be made close to the work |

Most mature enterprises evolve toward a hybrid of centralized and federated over time: central standards and high-risk oversight, federated execution in business units.

**Key roles.** Regardless of model, the following accountabilities must be assigned:

- **Chief AI Officer (CAIO) or equivalent.** Accountable for AI strategy execution and AI governance program. Not necessarily a separate role from the CISO or CTO, but the accountability must be named.
- **Model Risk Officers.** Own the model inventory, validation program, and model change management process. In regulated industries, these are formal roles with defined independence from model development.
- **Responsible AI Lead.** Owns the bias, fairness, and ethics dimension of AI governance — the part of governance that cannot be fully addressed by technical controls alone.
- **AI Governance Board or Committee.** Senior cross-functional body that reviews high-risk AI deployments, approves exceptions, and owns AI policy at the organizational level. Provides the governance connection to the board.

For organizations building this function, see the [practitioner guide to standing up an AI governance function](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/04-practitioner-guide-standing-up-an-ai-governance-function.md).

---

## Common Failure Modes

AI governance fails in patterns. These are the four that account for most of it.

**Governance theater.** Policies exist, committees meet, and documentation is produced — but enforcement is nominal. AI systems go to production without completing the validation process. Exceptions become the rule. The acceptable use policy is posted on the intranet but never enforced. Governance theater is often the result of governance being funded as a compliance activity rather than a risk management activity: the goal is to have the artifacts, not to manage the risk the artifacts are supposed to control.

**Speed-vs.-safety resolved the wrong way.** A business unit wants to ship a model quickly. The governance process is slow. The business unit deploys without completing governance, or governance is abbreviated to the point of meaninglessness. This pattern is so common it has a structural cause: governance is a cost center, and the cost is visible; risk is distributed across future events, and the cost is not. The fix is not to slow down deployment — it is to make governance fast enough to be compatible with the speed of delivery. Lightweight governance for low-risk models, rigorous governance for high-risk ones. Calibration, not uniformity.

**Agentic blind spots.** The governance frameworks most enterprises have built were designed for predictive models and generative AI assistants: systems that produce outputs for human review before action. Agentic AI — autonomous systems that take actions in the world on behalf of the enterprise — requires a fundamentally different governance model. An agent that sends emails, modifies data, executes transactions, or calls APIs is not producing a recommendation for review; it is acting. The governance question is no longer "is this output accurate enough?" but "is this action reversible, authorized, and bounded?" Most governance frameworks in place today do not answer that question.

> **74%** of companies expect to be using AI agents within two years; only **21%** have a mature governance model for agentic AI in place ([Deloitte, 2026](#ev-deloitte-state-ai-enterprise-2026-agentic-governance-gap))

**Vendor pass-through.** An enterprise deploys a third-party AI product that produces discriminatory outputs. When challenged, the enterprise's answer is "we relied on the vendor's compliance attestations." In most legal and regulatory frameworks, this is not a defense. The enterprise deploying the AI system is the deployer of record, and deployer obligations — including EU AI Act deployer obligations under Article 26 — attach to the deployer, not just the developer. Assuming the vendor handles compliance is the most expensive governance assumption an enterprise can make.

---

## Governance Readiness Checklist

- [ ] An AI model inventory exists, covers all production models including third-party APIs, and is actively maintained
- [ ] A model risk tiering methodology is in place; high-risk models have defined validation and approval requirements before deployment
- [ ] Performance monitoring and drift detection is active for production models, with defined thresholds and escalation procedures
- [ ] An AI vendor risk questionnaire (AI-specific, not generic IT security) is used for all AI vendors and embedded AI products
- [ ] AI vendor contracts include model change notification rights, data handling protections, and defined SLAs for model behavior
- [ ] An acceptable use policy exists, is specific enough to be enforceable, and covers prohibited uses explicitly
- [ ] Human-in-the-loop requirements are defined for consequential AI use cases (credit, employment, healthcare, legal) with named review accountabilities
- [ ] Escalation paths are documented and known to front-line AI users
- [ ] An AI governance role or function is named and resourced (CAIO, model risk officer, responsible AI lead, or equivalent)
- [ ] EU AI Act applicability has been assessed; high-risk systems have been identified and compliance preparation is underway
- [ ] AI governance coverage explicitly addresses agentic and autonomous AI systems, not only predictive and generative models

Assess governance maturity against the companion [governance maturity scoring assessment](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/05-assessment-governance-maturity-scoring.md). For the data layer that underpins governance, see [Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md).

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **AuditBoard — *From blueprint to reality: Execute effective AI governance in a volatile landscape*, 2025.** 82% say they're using AI across functions, yet only 25% report that they have a fully implemented AI governance program. [View source](https://auditboard.com/resources/ebook/from-blueprint-to-reality-execute-effective-ai-governance-in-a-volatile-landscape){#ev-auditboard-blueprint-to-reality-2025-governance-gap} · verified 2026-06-21 · primary
- **IBM (Ponemon Institute) — *Cost of a Data Breach Report 2024*, 2024.** The global average cost of a data breach reached USD 4.88 million in 2024, a 10% increase from the prior year and the largest yearly jump since the pandemic. [View source](https://newsroom.ibm.com/2024-07-30-ibm-report-escalating-data-breach-disruption-pushes-costs-to-new-highs){#ev-ibm-cost-of-breach-2024-average-cost} · verified 2026-06-21 · primary
- **McKinsey — *The State of AI*, 2025.** 88% of respondents report regular AI use in at least one business function, compared with 78% a year ago. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-adoption} · verified 2026-06-20 · primary
- **McKinsey — *The State of AI: How Organizations Are Rewiring to Capture Value*, 2024.** 78% of organizations now use AI in at least one business function (up from 72% in early 2024 and 55% in 2023). [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-how-organizations-are-rewiring-to-capture-value){#ev-mckinsey-state-of-ai-2024-adoption} · verified 2026-06-22 · primary
- **McKinsey — *State of AI Trust in 2026: Shifting to the Agentic Era*, 2026.** Only about one-third of organizations report maturity levels of three or higher in strategy, governance, and agentic AI governance; average responsible-AI maturity rose to 2.3 in 2026 from 2.0 in 2025. [View source](https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/tech-forward/state-of-ai-trust-in-2026-shifting-to-the-agentic-era){#ev-mckinsey-trust-2026-maturity-level-three} · verified 2026-06-21 · ⚠ secondary mirror
- **Ncontracts — *2025 Third-Party Risk Management Survey*, 2025.** 49% of financial institutions experienced a vendor-related cyber incident in the past year. [View source](https://www.ncontracts.com/nsight-blog/ncontracts-2025-third-party-risk-management-survey){#ev-ncontracts-tprm-survey-2025-vendor-cyber-incident} · verified 2026-06-21 · primary
- **Ncontracts — *2025 Third-Party Risk Management Survey*, 2025.** Nearly three-quarters of respondents (73%) have two or fewer full-time employees managing vendor risk, even though more than half oversee more than 300 vendors. [View source](https://www.ncontracts.com/nsight-blog/ncontracts-2025-third-party-risk-management-survey){#ev-ncontracts-tprm-survey-2025-vendor-risk-staffing} · verified 2026-06-21 · primary
- **European Commission — *Regulatory framework on AI (Regulation (EU) 2024/1689)*, 2024.** the governance rules and the obligations for general-purpose AI models became applicable on 2 August 2025; the majority of remaining obligations, including rules for high-risk AI systems, apply from 2 August 2026. [View source](https://digital-strategy.ec.europa.eu/en/policies/regulatory-framework-ai){#ev-ec-ai-act-2024-application-timeline} · verified 2026-06-21 · primary
- **European Union — *Regulation (EU) 2024/1689 (AI Act), Article 99*, 2024.** administrative fines of up to 35 000 000 EUR or up to 7% of total worldwide annual turnover (whichever is higher) for prohibited practices; up to 15 000 000 EUR or 3% for breaches of operator obligations (Articles 16, 26 and others); up to 7 500 000 EUR or 1% for incorrect or misleading information. [View source](https://artificialintelligenceact.eu/article/99/){#ev-eu-ai-act-2024-article-99-penalties} · verified 2026-06-21 · primary
- **IBM Institute for Business Value — *The CAIO Study: How Chief AI Officers deliver AI ROI (with Dubai Future Foundation and Oxford Economics)*, 2025.** 26% of organizations currently have a Chief AI Officer, up from 11% in 2023. [View source](https://www.ibm.com/thought-leadership/institute-business-value/en-us/report/chief-ai-officer){#ev-ibm-caio-study-2025-caio-adoption} · verified 2026-06-21 · ⚠ secondary mirror
- **McKinsey — *The State of AI: How Organizations Are Rewiring to Capture Value*, 2025.** Only 28% of companies report that their CEO directly oversees AI governance (and just 17% report that their board does). [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai-how-organizations-are-rewiring-to-capture-value){#ev-mckinsey-rewiring-2025-ceo-oversight} · verified 2026-06-20 · primary
- **Deloitte — *State of AI in the Enterprise 2026 (Agentic AI is scaling faster than guardrails)*, 2026.** By 2027, 74% of respondents expect their companies to be using AI agents at least moderately, but only 21% say their organizations have a mature governance model in place for agentic AI. [View source](https://www.deloitte.com/us/en/insights/topics/emerging-technologies/ai-agents-scaling-faster.html){#ev-deloitte-state-ai-enterprise-2026-agentic-governance-gap} · verified 2026-06-21 · primary
