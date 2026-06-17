---
type: Reference
title: Tooling Landscape
description: AI governance platforms, model monitoring and observability tools, regulatory compliance management, and audit and explainability tools.
tags: [ai-governance, tooling, model-monitoring, compliance, explainability]
timestamp: "2026-06-16"
---

## How to Use This Landscape

This is a survey of the platforms and tools that support the work of this track — governing AI systems, managing model risk, meeting regulatory obligations, and building the audit record that regulators and internal stakeholders increasingly expect. Pair it with the three working pages it supports: [the core framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/core-framework.md) (what good governance contains), [the practitioner guide](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/practitioner-guide-standing-up-an-ai-governance-function.md) (how to build the governance function), and [the assessment](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/assessment-governance-maturity-scoring.md) (how to score where you stand).

One honest caveat up front: the AI governance tooling market is immature and consolidating rapidly. As of mid-2026 most enterprises are assembling solutions from three or four specialized tools rather than buying one platform that handles everything — monitoring here, policy management there, explainability from a third vendor. Many of the tools below address model monitoring and observability well; the policy, regulatory compliance, and audit-trail layers are served by a thinner, earlier-stage set of products. Buy accordingly: evaluate for the specific gap you need to fill, not for an "AI governance" label.

---

## AI Governance Platforms

Purpose-built platforms that attempt to govern AI systems across the full lifecycle — from model registration and policy assignment through to production monitoring and compliance reporting. These go beyond point-solutions by providing a record of governance decisions, not just operational metrics.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[Credo AI](https://www.credo.ai)** | Policy management and model assessment platform that maps AI systems to policies, generates governance reports, and surfaces risk scores against configurable compliance frameworks (EU AI Act, NIST AI RMF, internal standards). Connects to model registries and monitoring tools to pull evidence automatically. | Enterprises that need a governance record-of-decisions layer on top of existing MLOps tooling, particularly those facing regulatory scrutiny or board-level reporting requirements. |
| **[IBM OpenPages with AI Governance](https://www.ibm.com/products/openpages)** | IBM's GRC platform extended with AI-specific governance capabilities: model inventory, factsheets (structured documentation of model lineage, training data, and risk), bias and drift monitoring via IBM Watson Studio integration, and regulatory mapping. Originally IBM Watson OpenScale, now folded into the OpenPages suite. | Large enterprises in regulated industries (financial services, healthcare) that already run IBM infrastructure and need governance integrated into existing GRC workflows. |
| **[DataRobot MLOps](https://www.datarobot.com/platform/mlops/)** | End-to-end MLOps platform with built-in governance features: model registry with lineage tracking, automated bias and drift monitoring, challenger testing, and compliance reporting dashboards. Positions governance as a built-in feature rather than an add-on. | Enterprises that want a single platform spanning model development, deployment, monitoring, and governance; less suited to organizations deploying models from external vendors or large language models. |
| **[Weights & Biases (W&B)](https://wandb.ai)** | Experiment tracking, model registry, and lineage platform with governance-oriented features including model versioning, lineage graphs, automated audit logs of training runs, and access controls on model artifacts. Stronger on the pre-production governance side (what went into a model) than the post-production compliance side. | ML engineering teams that need a governed model registry and full training-run audit trail; often paired with a separate monitoring tool for production governance. |

---

## Model Monitoring and Observability

Tools specifically designed for detecting what goes wrong with models after deployment: performance degradation, data drift, concept drift, bias emergence, and data quality failures. These are distinct from general infrastructure observability — they understand model inputs, outputs, and ground-truth labels, not just CPU and latency.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[Arize AI](https://arize.com)** | ML observability platform providing real-time drift detection, embedding analysis, bias monitoring, and root-cause analysis for model performance issues. Supports both traditional ML and LLM monitoring (hallucination scoring, retrieval quality). | Teams running models in production at scale who need deep observability across structured and unstructured model types, including LLMs. |
| **[WhyLabs](https://whylabs.ai)** | Data and ML monitoring platform using statistical profiling (whylogs) to track data distributions and model outputs over time. Detects drift and data quality issues with low-overhead logging. Includes LLM monitoring for hallucination, toxicity, and prompt injection. | Organizations that want lightweight, open-standards-based monitoring with minimal integration overhead; good fit for teams who want to own the profiling logic via the open-source whylogs library. |
| **[Evidently AI](https://www.evidentlyai.com)** | Open-source ML monitoring library and platform for generating drift, bias, and data quality reports. The open-source core produces detailed HTML reports for batch evaluation; the cloud product adds real-time monitoring dashboards. | Teams wanting open-source, auditable monitoring code that produces shareable reports — useful for governance workflows where evidence must be produced and stored, not just displayed. |
| **[Aporia](https://www.aporia.com)** | Real-time ML monitoring platform with automated root-cause analysis, bias detection, and model behavioral guardrails. Includes LLM monitoring and a policy engine for blocking or flagging violating model outputs in production. | Organizations deploying LLMs in customer-facing applications that need real-time guardrails on model behavior, not just retrospective drift reporting. |
| **[Fiddler AI](https://www.fiddler.ai)** | Model monitoring and explainability platform combining production monitoring (drift, performance, bias) with built-in explainability (feature attribution via SHAP) surfaced in a unified interface. Targets regulated industries with compliance-oriented audit trail features. | Regulated-industry deployments where monitoring and explainability evidence must be available together for model risk management or regulatory examination. |
| **[Arthur AI](https://www.arthur.ai)** | Model monitoring platform with bias detection, performance tracking, and explainability. Covers structured ML and NLP/LLM use cases, with LLM-specific metrics for hallucination and faithfulness scoring. | Enterprise teams needing a vendor-supported monitoring layer across both classical ML and generative AI models. |
| **Grafana + Prometheus** | General-purpose observability stack widely used for infrastructure metrics. Can monitor ML model endpoints by exposing custom metrics (prediction counts, confidence distributions, latency) via standard instrumentation libraries. Requires custom integration work to surface model-specific signals like drift or bias. | Teams that already run Grafana/Prometheus infrastructure and want to pull model health metrics into existing dashboards; not a substitute for model-specific observability tooling when bias or drift detection is required. |

---

## Regulatory Compliance and Policy Management

Tools for managing the compliance obligations, policy documentation, and regulatory workflows that AI governance programs must handle — particularly the EU AI Act, sector-specific rules, and internal acceptable-use policies. This is the least mature category: most "AI compliance" products are either early-stage startups or extensions of general GRC platforms. Expect to assemble rather than buy.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[OneTrust](https://www.onetrust.com/solutions/ai-governance/)** | Privacy and data governance platform that has extended into AI governance with modules for AI system inventory, EU AI Act risk classification, data processing assessments, and policy management. The privacy and data governance capabilities are mature; the AI-specific modules are newer additions. | Enterprises already using OneTrust for privacy management that want to extend the same inventory and workflow tooling to AI systems; a pragmatic choice for organizations that need EU AI Act workflows without buying a separate platform. |
| **[TrustArc](https://trustarc.com)** | Privacy management platform with AI governance extensions covering AI risk assessment, policy documentation, and compliance workflow management. Similar in scope to OneTrust's AI modules; less market presence in the AI governance space specifically. | Enterprises running TrustArc for privacy compliance that want to add structured AI governance workflows without standing up a separate tool. |
| **[Saidot](https://www.saidot.ai)** | Purpose-built EU AI Act compliance platform for AI system registration, risk classification, conformity assessment workflows, and generating the technical documentation required for high-risk AI systems. One of the few tools designed specifically around the EU AI Act's structure. | Organizations that need to work through EU AI Act compliance processes specifically — high-risk AI system classification, conformity assessments, and the required technical documentation. |
| **[ServiceNow GRC](https://www.servicenow.com/products/governance-risk-and-compliance.html)** | Enterprise GRC platform with AI governance extensions. Manages policies, control frameworks, risk registers, and audit workflows. AI governance is implemented as a content layer on the existing GRC platform rather than purpose-built functionality. | Large enterprises already running ServiceNow that want to extend existing GRC processes and workflows to cover AI systems; relies on policy content and configuration rather than purpose-built AI governance logic. |

---

## Audit and Explainability Tools

Tools for producing the technical explanations, bias assessments, and documentation artifacts that governance programs, model risk management frameworks, and regulators require. Most of these are open-source libraries — the ecosystem here is richer and more mature than in the compliance management category.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[SHAP](https://shap.readthedocs.io)** (SHapley Additive exPlanations) | The industry-standard library for local and global model explainability, decomposing predictions into per-feature contributions using game-theoretic Shapley values. Supported natively by most ML platforms and many monitoring tools. | Any use case where per-prediction explanation is required — regulatory examination, model risk management documentation, or debugging model behavior. Should be the default explainability method unless there's a specific reason to use another. |
| **[LIME](https://github.com/marcotcr/lime)** (Local Interpretable Model-agnostic Explanations) | Generates local, approximate explanations for individual predictions by fitting an interpretable model around the prediction point. More intuitive in some settings than SHAP; less consistent across runs. | Cases where a simpler, locally-interpretable explanation is preferred and SHAP's computational cost is prohibitive; also useful as a cross-validation check against SHAP outputs. |
| **[IBM AI Fairness 360](https://aif360.res.ibm.com)** | Open-source Python library providing over 70 fairness metrics and more than 10 bias mitigation algorithms. Covers pre-processing (data rebalancing), in-processing (constrained training), and post-processing (output calibration) interventions. | Teams that need to measure, document, and mitigate bias across protected attributes — lending, hiring, healthcare risk scoring, and other regulated use cases. The toolkit is well-documented and actively used in financial services model risk management. |
| **[Microsoft Responsible AI Toolbox](https://responsibleaitoolbox.ai)** | An integrated open-source dashboard combining fairness assessment (Fairlearn), error analysis, interpretability (SHAP/LIME), and causal analysis in a single interface. Designed to make governance evidence-gathering a coherent workflow rather than running separate libraries. | Teams using Azure ML or wanting an integrated interface for producing governance evidence across multiple dimensions — fairness, error patterns, and explanations — in one place. |
| **[Google Model Cards Toolkit](https://github.com/tensorflow/model-card-toolkit)** | A library for generating structured model cards — standardized documentation of a model's intended use, evaluation results, fairness considerations, and known limitations. Model cards are increasingly expected by regulators and procurement processes. | Organizations that need to produce and maintain standardized model documentation at scale; also useful for internal governance workflows that require a documented record of what each model does and its known limitations. |
| **[MLflow](https://mlflow.org)** | Open-source platform for experiment tracking, model registry, and deployment. The model registry provides versioned artifact storage with metadata and serves as the audit trail for model lineage — what data was used, what parameters were set, and who promoted a model to production. | Any team that needs a governed model registry with full training-run audit history; MLflow's ubiquity makes it a natural foundation for governance workflows, and it integrates with most ML platforms. |

---

## References

- Credo AI — *AI Governance Platform* documentation and product materials
- IBM — *IBM OpenPages with AI Governance* and IBM Watson OpenScale product documentation
- DataRobot — *MLOps and AI Governance* documentation
- Weights & Biases — *W&B Registry* and experiment tracking documentation
- Arize AI — *ML Observability* product materials
- WhyLabs — *AI Observability Platform* and whylogs open-source library documentation
- Evidently AI — *Open-Source ML Monitoring* documentation
- Aporia — *Real-Time ML Monitoring* product materials
- Fiddler AI — *Model Monitoring and Explainability* documentation
- Arthur AI — *ML Monitoring* product documentation
- OneTrust — *AI Governance* module documentation
- Saidot — *EU AI Act Compliance Platform* product materials
- Lundberg & Lee — *A Unified Approach to Interpreting Model Predictions* (SHAP), NeurIPS 2017
- Ribeiro, Singh & Guestrin — *"Why Should I Trust You?": Explaining the Predictions of Any Classifier* (LIME), KDD 2016
- Bellamy et al. — *AI Fairness 360: An Extensible Toolkit for Detecting, Understanding, and Mitigating Unwanted Algorithmic Bias*, IBM Research 2018
- Google — *Model Cards for Model Reporting*, FAccT 2019
- MLflow — *MLflow: A platform for the machine learning lifecycle* documentation
- Microsoft — *Responsible AI Toolbox* documentation and Fairlearn library
