---
type: Reference
title: Glossary
description: A practitioner glossary of AI and data terms used across the framework — fundamentals, agents, governance, architecture, lineage, infrastructure, security, and integration.
tags: [glossary, reference, ai, governance]
timestamp: "2026-06-12"
status: published
appendix: true
---

A running glossary of AI and data terms — added to as we build out each component. Definitions are written for practitioners, not academics.

---

## Table of Contents

- **Section 1** — AI & ML Fundamentals: Training, ML, Generative AI, Weights, Ground Truth, Label, Label Noise, Data Drift, Inference, RAG, Hallucination, Feature, Feature Store
- **Section 2** — Agents, Automations & Workflows: Agent, Agentic Workflow, Automation vs. AI, Orchestration, Tool Use, Multi-Agent System, HITL, Context Window, System Prompt, Memory, Grounding, Deterministic vs. Probabilistic, Training-Serving Skew, Interrupt-Diagnose-Correct-Verify
- **Section 3** — Governance, Compliance & Accountability: Data Owner, Data Steward, Data Custodian, CDAO, DPO, Governance Council, Model Card, DPIA, Policy as Code, NIST AI RMF, EU AI Act, ISO/IEC 42001, Explainability, Auditability, Fairness Metrics, Prompt Injection
- **Section 4** — Data Architecture & Integration: Data Silo, ETL/ELT, Data Catalog, API, Data Lake, Data Warehouse, Data Lakehouse, Schema
- **Section 5** — Lineage, Metadata & Semantic Layer: Data Lineage, Metadata, Data Dictionary, Vector Embedding, Vector Store
- **Section 6** — Infrastructure & Operations: MLOps, CI/CD, Token/Tokenization, Latency
- **Section 7** — Security, Privacy & Compliance: RBAC, PII, PHI, Data Masking, Anonymization vs. Pseudonymization, Consent Management
- **Section 8** — Integration Patterns & Architecture: CDC, Event Streaming, Data Virtualization, Data Fabric, Data Mesh, Semantic Layer, Data Product
- **Section 11** — Security Threats: Data Poisoning, Model Inversion, Membership Inference, Differential Privacy, Federated Learning, Synthetic Data, Data Minimization, AI Supply Chain Attack, Purpose Limitation, Right to Erasure, ABAC, Inference Data Leakage, Zero Trust
- **Section 12** — Terms, Abbreviations & Acronyms: GDPR, CCPA, HIPAA, SLA, KPI, MTTD, MTTR, YAML, ODCS, GAN, TSTR/TRTS, IAA, Cohen's Kappa, Krippendorff's Alpha, NLP, NER, CRM, ERP, Golden Record, Survivorship Rules, ADAS, MAL, SPC, SMOTE, SHAP, LIME, CAGR, ICP, DBA, git

---

## Training

The process of exposing a model to data so it learns patterns, relationships, or behaviors — rather than being explicitly programmed with rules.

Instead of writing "if the email contains 'Nigerian prince', mark as spam," you show the model 10 million labeled emails and let it figure out the patterns itself. The model adjusts its internal parameters (weights) to minimize prediction error, repeated across millions of examples until the error is acceptably low.

---

## ML (Machine Learning)

A category of AI where models learn from labeled examples — inputs paired with correct outputs. Training is fundamentally an optimization problem: minimize the gap between the model's predictions and the known correct answers.

**Examples:** a fraud detection model trained on transactions labeled fraud/not-fraud; a churn model trained on customer behavior labeled churned/retained.

**Data quality dependency:** the model can only be as good as the ground truth it learned from. Garbage labels = garbage model.

---

## Generative AI (LLMs)

A category of AI model that generates new content (text, images, code) rather than predicting a label. Training happens in stages:

- **Pre-training** — the model is fed an enormous corpus (much of the internet, books, code) and learns to predict the next token. No human labels required. The model learns grammar, facts, and reasoning patterns purely from statistical patterns across billions of examples. This is what costs tens of millions of dollars in compute.
- **Fine-tuning** — the pre-trained model is further trained on a narrower, curated dataset to specialize it for a task or domain.
- **RLHF (Reinforcement Learning from Human Feedback)** — humans rate model outputs, and those ratings are used to tune the model toward helpful, accurate, and safe responses.

---

**Why data quality hits differently:** For classical ML, bad data produces a bad model for a specific task — bounded damage. For LLMs, bad pre-training data at scale encodes systematic biases, factual errors, and harmful patterns into the model's foundational weights, which are very hard to fully remove later. The corpus *is* the model's world knowledge.

## Weights / Parameters

The internal numerical values a model adjusts during training. Think of them as the knobs the model turns to get better at its task. A large language model has billions of these. Once training is complete, the weights are frozen and the model uses them to make predictions or generate outputs.

---

## Ground Truth

The correct, verified answer used to train or evaluate a model. In supervised learning, ground truth is the label a human (or trusted system) has assigned to a training example. Model accuracy is measured against ground truth — so the quality of the ground truth directly determines the ceiling of what the model can learn.

---

## Label / Annotation

The tag or classification applied to a training example to tell the model what the correct answer is. "This email is spam." "This image contains a cat." "This transaction is fraudulent."

Labeling is often done by humans and is expensive, slow, and error-prone. Label quality is one of the highest-leverage data quality investments in a supervised ML project.

---

## Label Noise

Errors or inconsistencies in training labels. Occurs when human annotators disagree, apply guidelines inconsistently, or make mistakes. Model performance degrades substantially when more than \~20% of training data is mislabeled. Even widely-used benchmark datasets like ImageNet contain significant numbers of mislabeled samples.

---

## Data Drift

The gradual shift in real-world data distributions over time, which causes a trained model's performance to degrade without any change to the model itself. Three forms:

- **Covariate shift** — the distribution of input features changes (e.g., the customer demographic mix of your user base evolves)
- **Prior shift** — the distribution of labels changes (e.g., fraud rate increases; the model wasn't trained on the new base rate)
- **Concept drift** — the relationship between features and labels changes (e.g., what predicts churn shifts after a product redesign)

---

## Inference

Using a trained model to make predictions or generate outputs on new data. Training happens once (or periodically); inference happens continuously in production. Data quality at inference time matters as much as at training time — a clean model fed dirty real-world data still produces bad outputs.

---

## RAG (Retrieval-Augmented Generation)

An architecture for GenAI applications where the model's response is grounded by retrieving relevant documents from an external knowledge base at query time, rather than relying solely on what was baked into the model during training. Reduces hallucination and keeps responses current without retraining.

**Data quality dependency:** the quality of the retrieved documents directly determines the quality of the response. A RAG system is only as good as the corpus it retrieves from.

---

## Hallucination

When a generative AI model produces confident, fluent output that is factually incorrect or entirely fabricated. A consequence of the model optimizing for plausible-sounding text rather than verified truth. Hallucination is one of the primary governance risks in GenAI deployments and has no direct analog in classical ML.

---

## Feature

An individual measurable variable used as input to a model. In a churn prediction model, features might include: days since last login, number of support tickets, contract type, monthly spend. Feature quality — whether the feature is accurate, fresh, and well-defined — directly impacts model quality.

---

## Feature Store

A centralized repository for storing, versioning, and serving ML features. Ensures that the same feature definitions and transformations are used consistently during training and inference, preventing training-serving skew. A key piece of MLOps infrastructure for organizations running multiple models at scale.

---

## SECTION 2 — Agents, Automations & Workflows

These terms cover how AI actually *acts* on data in production — the consumption layer that data readiness ultimately serves. If the infrastructure terms above describe what data needs to look like, these terms describe what happens when that data meets an AI system doing real work.

---

## Agent (AI Agent)

A software system that perceives its environment, makes decisions, and takes actions to achieve a goal — often autonomously and across multiple steps. Unlike a simple chatbot that responds to a single prompt, an agent can plan, use tools, check its own work, and loop until a task is complete.

**What makes it an agent vs. a chatbot:** an agent has access to tools (search, write to a database, send an email, call an API), maintains state across steps, and can decide *which* tool to use *when* based on the goal.

**Data readiness connection:** an agent is only as reliable as the data it can access and the tools it can call. Poor data quality at the tool layer produces compounding errors — the agent makes a decision based on bad data, takes an action based on that decision, and the error propagates downstream before any human reviews it.

---

## Agentic Workflow

A multi-step process where one or more AI agents execute a sequence of actions — often with branching logic, tool calls, and checkpoints — to complete a complex task. Agentic workflows go beyond single prompt-response interactions.

**Example:** a lead enrichment workflow where an agent (1) pulls a new CRM contact, (2) searches the web for company context, (3) scores the lead against ICP criteria, (4) drafts a personalized outreach email, and (5) adds it to the send queue — all without human intervention per lead.

**Why it matters for data readiness:** agentic workflows are the primary reason organizations need AI-ready data *now*. The workflow is only as reliable as its weakest data input. One stale field, one missing permission, one inconsistent schema can break the entire chain.

---

## Automation vs. AI

Often used interchangeably but meaningfully different:

- **Automation** is deterministic — it follows explicit rules. "If invoice total \> \$10,000, route to CFO for approval." The same input always produces the same output. No learning involved.
- **AI** is probabilistic — it makes predictions or generates outputs based on learned patterns. The same input can produce different outputs depending on context, and the model's behavior can change as it's retrained.

Most real-world AI systems combine both: a deterministic workflow orchestrates steps and routes data, while AI models handle the judgment calls within that workflow.

---

## Orchestration

The coordination layer that manages the sequence, routing, and execution of steps in an agentic workflow. The orchestrator decides what runs next, passes data between steps, handles errors, and enforces timeouts and retries.

**Examples:** LangChain, LangGraph, CrewAI, Temporal, Airflow (for data pipelines). In agentic systems, the orchestrator is what turns a collection of tools and models into a coherent workflow.

**Data readiness connection:** orchestration frameworks need clean, well-typed data contracts between steps. If one step outputs data in an unexpected format or with missing fields, the orchestrator either fails or passes bad data forward silently.

---

## Tool Use (Function Calling)

The ability of an AI model to call external functions or APIs as part of generating a response. Instead of just producing text, the model can invoke a tool — search the web, query a database, run a calculation, write a file — and incorporate the result into its output.

Tool use is what transforms a language model from a text generator into an agent capable of taking real-world actions.

**Data readiness connection:** every tool call is a data access event. The quality, freshness, and permissions of the data returned by that tool directly shape the model's next decision.

---

## Multi-Agent System

An architecture where multiple specialized AI agents collaborate to complete a task — each handling a specific domain or step, passing outputs to the next agent. One agent might research, another reason, another write, another review.

**Why it matters:** multi-agent systems amplify both the benefits and the risks of individual agents. Data quality errors propagate faster and farther. Governance and observability become significantly more complex — you need to trace not just model inputs and outputs but inter-agent handoffs.

---

## Human-in-the-Loop (HITL)

A design pattern where a human is inserted at specific points in an agentic workflow to review, approve, or correct the AI's output before it proceeds. A safety mechanism for high-stakes decisions.

**Example:** an agent drafts a contract amendment and flags it for legal review before sending. The human approves or edits, then the workflow continues.

HITL is not a permanent solution for bad data quality — it's an operational control. Over-reliance on HITL to catch data errors signals that upstream readiness work is incomplete.

---

## Context Window

The maximum amount of text (or tokens) an LLM can "see" and reason over at one time. Think of it as the model's working memory for a single interaction. Everything the model knows about the current task must fit within this window — including the system prompt, conversation history, retrieved documents, and tool outputs.

**Why it matters for data readiness:** what goes into the context window *is* the data the model acts on. Irrelevant, redundant, or low-quality content in the context window degrades response quality just as bad training data degrades model quality. Context curation is a data quality problem.

---

## System Prompt

Instructions given to an AI model at the start of every interaction that define its role, constraints, tone, and behavior. The system prompt is typically invisible to the end user but shapes every response the model produces.

In agentic systems, the system prompt often includes tool definitions, workflow rules, and domain-specific knowledge the agent needs to operate correctly.

---

## Memory (Short-Term vs. Long-Term)

- **Short-term memory** — what the model holds in its context window during a single session. Ephemeral; disappears when the session ends.
- **Long-term memory** — information persisted to an external store (database, vector store) and retrieved into context when relevant. Enables agents to "remember" past interactions, user preferences, or accumulated knowledge across sessions.

Long-term memory is a data management problem as much as a technical one. What gets stored, how it's indexed, how it's retrieved, how it's kept current — these are data readiness questions.

---

## Grounding

The practice of anchoring an AI model's outputs to verified, specific data sources rather than relying on general training knowledge. RAG is the most common grounding technique. Grounding reduces hallucination and keeps responses factually current.

**Ungrounded:** "What is our Q2 revenue?" → model generates a plausible-sounding number from training data.

**Grounded:** "What is our Q2 revenue?" → model retrieves the actual Q2 report from the data source and answers from it.

---

## Deterministic vs. Probabilistic

- **Deterministic:** given the same input, always produces the same output. Traditional software, rules engines, and automations are deterministic.
- **Probabilistic:** given the same input, may produce different outputs. AI models are probabilistic — they sample from a distribution of possible responses.

This distinction matters for testing, auditing, and governance. You can't unit-test an AI system the same way you test deterministic code. Data readiness for AI must account for this — quality checks need to be statistical and continuous, not binary pass/fail.

---

## Training-Serving Skew

A data quality failure where the data a model was trained on differs in distribution, format, or semantics from the data it receives during inference (serving). The model performs well in testing but degrades in production because production data doesn't look like training data.

One of the most common and costly AI deployment failures. Prevented by enforcing consistent feature engineering pipelines across training and serving, and by monitoring production data distributions continuously.

---

## Interrupt-Diagnose-Correct-Verify Loop

A workflow pattern for AI systems that operate on streaming or real-time data. When the model detects an anomaly or low-confidence situation, it interrupts the normal flow, diagnoses the issue, applies a correction, and verifies the result before continuing. Used in quality control, real-time coaching, and monitoring systems.

Requires high-quality, low-latency data pipelines — the loop only works if the data the model is interrupting on is trustworthy and fresh.

---

## SECTION 3 — Governance, Compliance & Accountability

Terms introduced in Component 02 — Data Governance.

---

## Data Owner

A business leader accountable for data assets within their domain. Sets access policy, approves usage, and owns quality outcomes. Distinct from the technical teams who store or move the data — the owner is the business decision-maker, not the engineer.

---

## Data Steward

A subject matter expert who executes day-to-day data quality management within a domain. Defines standards, documents lineage, flags issues, and acts as the bridge between business requirements and technical implementation. One steward per domain is the standard model.

---

## Data Custodian

The technical role responsible for storing, moving, and securing data assets. Implements the policies that data owners and stewards define. Often an engineer or DBA. Does not set policy — enforces it.

---

## CDAO (Chief Data & Analytics Officer)

The executive responsible for enterprise-level data governance, data strategy, and AI governance alignment. Increasingly accountable for AI outcomes as well as data management. In many organizations, this role has expanded from managing data infrastructure to owning AI risk.

---

## DPO (Data Protection Officer)

The role (required by law in many jurisdictions under GDPR) responsible for ensuring compliance with data privacy regulations. In AI contexts, the DPO reviews training data sourcing, consent management, and data subject rights across AI pipelines.

---

## Governance Council

A cross-functional body — typically including data, legal, compliance, engineering, and risk — that sets AI governance policy, resolves conflicts, and reviews high-risk AI use cases before deployment. The key structural mechanism for distributing accountability without creating bottlenecks.

---

## Model Card

A standardized document that summarizes what a model does, what data it was trained on, its known limitations, fairness testing results, performance benchmarks, and recommended use restrictions. The AI equivalent of a product spec sheet. Required by the EU AI Act for high-risk AI applications and increasingly expected by enterprise procurement processes.

---

## DPIA (Data Protection Impact Assessment)

A structured risk assessment required when personal data is involved in AI processing. Documents the nature of the data, the purpose of processing, risks to data subjects, and the mitigations in place. Required under GDPR for high-risk processing and referenced by the EU AI Act.

---

## Policy as Code

The practice of expressing governance policies as machine-executable rules embedded in infrastructure, rather than as documents enforced through manual review. Governance checks run automatically in CI/CD pipelines, data pipelines, and deployment systems. The only viable approach to governance at AI scale.

---

## NIST AI RMF (AI Risk Management Framework)

A voluntary US framework published by the National Institute of Standards and Technology for managing AI risk. Four core functions: **Govern** (establish accountability), **Map** (identify context and risk), **Measure** (analyze and assess risk), **Manage** (prioritize and treat risk). A GenAI Profile (AI 600-1, July 2024) adds 12 risk categories specific to LLMs and agents. Adoption satisfies an estimated 60–80% of requirements across EU AI Act, US state laws, and international standards simultaneously.

---

## EU AI Act

The first legally binding AI regulation, enacted by the European Union. Risk-based: the higher the potential harm of an AI system, the stricter the obligations. High-risk applications (credit scoring, HR, critical infrastructure) face the most demanding requirements — technical documentation, training data transparency, bias controls, and regulatory notification. Enforcement by the European Commission began August 2026.

---

## ISO/IEC 42001

An international standard that defines an auditable AI management system. Where NIST provides the risk methodology and the EU AI Act provides legal requirements, ISO 42001 provides the certifiable management system structure. The three frameworks are complementary layers of a single governance stack, not competing alternatives.

---

## Explainability

The ability to describe why an AI model produced a specific output in terms meaningful to the intended audience — a customer, regulator, or judge. A property of the model and its outputs. Distinct from auditability (which is a property of the governance infrastructure). Some model architectures (linear regression, decision trees) are inherently explainable; others (deep neural networks, LLMs) require additional techniques (SHAP, LIME, attention visualization) to generate post-hoc explanations.

---

## Auditability

The ability to reconstruct, after the fact, a complete and verifiable account of how an AI system made a specific decision — including the data it used, the model version, the policies in effect, and the access controls applied. A property of governance infrastructure (logs, lineage, documentation), not of the model itself. Regulators increasingly require operational evidence, not just policy declarations.

---

## Fairness Metrics

Quantitative measures used to evaluate whether an AI model treats different groups equitably. Common metrics include demographic parity (equal positive prediction rates across groups), equalized odds (equal true positive and false positive rates), and individual fairness (similar individuals treated similarly). Which metric applies depends on the use case — there is no single universal fairness definition, and different metrics can conflict with each other.

---

## Prompt Injection

An attack where malicious content embedded in data retrieved by an AI agent manipulates the agent's behavior — causing it to ignore its instructions, exfiltrate information, or take unauthorized actions. The AI equivalent of SQL injection. A significant governance risk in agentic systems that retrieve and process external content. Requires input sanitization and output monitoring at the agent layer.

---

## SECTION 4 — Data Architecture & Integration

Terms that will appear in Component 03 — Access & Integration.

---

## Data Silo

An isolated dataset or data system owned by one team or department that is inaccessible — technically or organizationally — to the rest of the organization. The most common structural barrier to AI readiness. Marketing has one customer record, operations has another, finance a third. AI systems that need a unified view of a customer, product, or process can't function when that data is fragmented across siloed systems that don't talk to each other.

---

## ETL / ELT

Two patterns for moving and transforming data between systems:

- **ETL (Extract, Transform, Load)** — data is extracted from source systems, transformed into the target format *before* being loaded into the destination. Traditional approach; transformation happens outside the warehouse.
- **ELT (Extract, Load, Transform)** — data is loaded raw into the destination first, then transformed in place using the warehouse's compute power. Modern approach enabled by cloud data warehouses (Snowflake, BigQuery, Databricks).

**AI relevance:** the transformation step is where data quality is either enforced or lost. Quality checks must be embedded in ETL/ELT pipelines — not bolted on afterward.

---

## Data Catalog

A system that maintains an inventory of all data assets in an organization — what data exists, where it lives, what it means, who owns it, how it's been used, and what its quality is. The navigational layer that makes data discoverable.

For AI, catalogs are essential for two reasons: (1) data scientists need to find relevant training data without relying on tribal knowledge, and (2) governance teams need visibility into what data is being used in which AI systems. Modern catalogs (Alation, Apache Atlas, Microsoft Purview, Atlan) automate discovery, capture lineage, and surface quality metrics.

---

## API (Application Programming Interface)

A defined interface that allows two software systems to communicate with each other. In the context of AI and data readiness, APIs are the primary mechanism by which AI agents access external data, call tools, and integrate with enterprise systems.

**Data readiness connection:** every API call is a data access event. The quality, freshness, latency, and governance of the data returned by an API directly affect the AI system consuming it. APIs without rate limits, versioning, or error handling create fragile data pipelines.

---

## Data Lake

A centralized storage repository that holds large volumes of raw data in its native format — structured, semi-structured, and unstructured — until it is needed. Designed for flexibility and scale.

**The AI problem with data lakes:** most enterprise data lakes were built with volume as the primary goal. Without quality controls, cataloging, and governance, they become "data swamps" — vast stores of data that are technically accessible but practically unusable for AI because no one knows what's in them, whether it's accurate, or how to find what they need.

---

## Data Warehouse

A structured repository optimized for analytical queries. Data is cleaned, transformed, and organized into well-defined schemas before being loaded. High quality and consistency, but less flexible than a data lake — only structured data, and transformations must be defined upfront.

**AI relevance:** warehouses (Snowflake, BigQuery, Redshift) are the most common source of structured training data for ML models. Their enforced schemas and quality standards make them more AI-ready than raw data lakes by default.

---

## Data Lakehouse

A modern architecture that combines the flexibility and scale of a data lake with the structure and governance of a data warehouse. Raw data is stored in open formats (Parquet, Delta, Iceberg), and a governance and query layer is applied on top.

The dominant enterprise AI data architecture in 2025–2026. Enables a single platform for both exploratory ML work (which needs raw data flexibility) and production AI (which needs governed, structured data).

---

## Schema

The formal definition of how data is structured — field names, data types, relationships between tables, and constraints. The schema is the contract that data must conform to.

**AI relevance:** schema inconsistencies across systems are one of the most common causes of training-serving skew and silent model failures. A field that is an integer in the training database but a string in the production API will break the pipeline — or worse, pass through silently and corrupt the model's inputs. Schema drift (when a schema changes unexpectedly) must be monitored continuously.

---

## SECTION 5 — Lineage, Metadata & Semantic Layer

Terms that will appear in Component 04 — Lineage & Metadata.

---

## Data Lineage

The documented record of a data asset's complete journey — where it originated, every transformation it has undergone, every system it has passed through, and every model or application that has consumed it. The evidence chain that makes AI explainable and auditable.

**Why it's non-negotiable for AI:** when a model produces a wrong or harmful output, lineage is what allows you to trace the error back to its source — a bad join, a mislabeled field, a stale data source. Without lineage, debugging model failures is guesswork. With it, root cause analysis is systematic.

---

## Metadata

Data about data. Describes the characteristics, context, and provenance of a data asset without being the data itself. Examples: the name of a database field, its data type, when it was last updated, who owns it, what business concept it represents, and what its known quality issues are.

**Two types relevant to AI:**

- **Technical metadata** — schema, data types, row counts, null rates, update frequency
- **Business metadata** — field definitions, business rules, ownership, usage context

AI systems depend on metadata to understand what data means, not just what it contains. A model trained on a field called `score` with no metadata has no way to know whether that's a credit score, an NPS score, or a game score.

---

## Data Dictionary

A reference document (or system) that defines every data field in an organization's data assets — its name, data type, allowed values, business definition, source system, and owner. The authoritative vocabulary for what data means.

For AI, the data dictionary is the foundation of consistent feature engineering. If two teams define "customer lifetime value" differently, models trained on each definition will behave differently — and comparisons between them will be meaningless.

---

## Vector Embedding

A numerical representation of a piece of content (text, image, audio) as a point in high-dimensional space, where semantically similar items are located near each other. The mathematical foundation of modern semantic search and RAG systems.

**Example:** the words "king," "queen," and "monarch" will have embeddings that are close together in vector space, even though the words are different strings. A RAG system uses embeddings to find documents that are *semantically* relevant to a query — not just lexically matching keywords.

**Data readiness connection:** the quality of embeddings depends directly on the quality of the content being embedded. Inconsistent, duplicate, or outdated documents in the corpus produce embeddings that retrieve the wrong content at query time.

---

## Vector Store (Vector Database)

A database purpose-built for storing and querying vector embeddings. Supports similarity search — finding the N nearest embeddings to a query vector — at scale and with low latency. The storage layer that makes RAG architectures practical.

**Examples:** Pinecone, Weaviate, Qdrant, pgvector (PostgreSQL extension), Chroma. Most major cloud data platforms now offer native vector search capabilities.

**Data readiness connection:** a vector store is only as useful as the embeddings it contains. Governance over what goes into the vector store — what documents are indexed, how they're chunked, when they're refreshed — is a data quality problem with direct consequences for RAG output quality.

---

## SECTION 6 — Infrastructure & Operations

Terms that will appear in Component 05 — Infrastructure Readiness.

---

## MLOps (Machine Learning Operations)

The discipline of applying DevOps principles — automation, continuous integration, monitoring, versioning — to the machine learning lifecycle. MLOps covers the full pipeline from data ingestion through model training, evaluation, deployment, monitoring, and retraining.

Without MLOps, ML models are research artifacts. With MLOps, they are production systems with the same operational standards as any other software: tested before deployment, monitored in production, versioned for rollback, and retired on a defined schedule.

**Key components:** experiment tracking, model registry, feature store, CI/CD for models, serving infrastructure, drift monitoring, automated retraining pipelines.

---

## CI/CD (Continuous Integration / Continuous Deployment)

A software engineering practice where code changes are automatically tested (CI) and deployed (CD) through a pipeline rather than manually. In the context of AI and data, CI/CD pipelines run quality checks, governance tests, and model evaluations automatically whenever data or code changes.

**AI relevance:** policy-as-code governance requires CI/CD. Quality checks embedded in the pipeline only work if that pipeline runs automatically and blocks bad changes from reaching production.

---

## Token / Tokenization

The unit by which LLMs process text. Tokenization is the process of splitting text into tokens — roughly word fragments — before feeding it to a model. "Tokenization" becomes approximately \["Token", "ization"\] depending on the model's vocabulary.

**Why it matters practically:**

- **Context window limits** are measured in tokens, not words or characters
- **LLM pricing** is typically per token (input + output)
- **Chunking strategies** for RAG must account for token limits when splitting documents

A rough rule of thumb: 1 token ≈ 0.75 words in English. A 100,000-token context window holds roughly 75,000 words — about the length of a novel.

---

## Latency

The time elapsed between a request being made and a response being received. In AI systems, latency has multiple components: data retrieval latency (how long to fetch context), model inference latency (how long the model takes to generate a response), and end-to-end latency (what the user experiences).

**Data readiness connection:** real-time AI applications (fraud detection, personalization, dynamic pricing) have hard latency requirements — often under 100ms. Meeting these requires data pipelines designed for low-latency access, not just high-throughput batch processing. A model that's accurate but too slow to respond within the decision window is operationally useless for real-time use cases.

---

## SECTION 7 — Security, Privacy & Compliance

Terms that will appear in Component 06 — Security & Compliance.

---

## RBAC (Role-Based Access Control)

An access control model where permissions to data and systems are assigned to roles rather than individual users. Users are assigned roles; roles carry permissions. A data scientist role might have read access to training datasets but not production customer data. An AI agent role might have write access to a specific output table but nothing else.

**AI relevance:** RBAC is the primary mechanism for enforcing least-privilege access in AI pipelines. Every component of an AI system — the training job, the inference service, the agent — should operate under a role with the minimum permissions required to complete its task.

---

## PII (Personally Identifiable Information)

Any data that can be used to identify a specific individual — name, email address, phone number, Social Security number, IP address, location data, biometric data, and combinations of fields that together identify someone even if none individually would.

**AI relevance:** PII in training data creates legal, ethical, and security risks. Models can memorize and reproduce PII from training data. Data pipelines feeding AI systems must identify, classify, and appropriately handle PII before it reaches any model — whether through masking, anonymization, or access restriction.

---

## PHI (Protected Health Information)

A subset of PII specifically covering health information that can be linked to an individual — diagnoses, treatment records, insurance information, lab results. Protected in the US by HIPAA and subject to strict handling requirements in most jurisdictions.

**AI relevance:** AI applications in healthcare and insurance require special data handling controls for PHI. Federated learning (training models without centralizing data) is one architectural approach to enable AI on PHI without the compliance risk of centralization.

---

## Data Masking

The process of replacing sensitive data values with realistic but fictional substitutes — preserving the data's format and statistical properties while making it impossible to identify real individuals. Used to create safe versions of production datasets for AI development and testing.

**Example:** a real customer record with name "Jane Smith" and SSN "123-45-6789" becomes "Sarah Jones" and "987-65-4321" in the masked development dataset. The model can train on realistic data without exposure to real PII.

---

## Anonymization vs. Pseudonymization

Two related but legally distinct techniques for protecting personal data:

- **Anonymization** — data is transformed so that individuals can no longer be identified, even by the data controller, by any means. Truly anonymized data falls outside GDPR scope. Very hard to achieve in practice — re-identification attacks on "anonymized" datasets are common.
- **Pseudonymization** — identifying fields are replaced with artificial identifiers (pseudonyms), but a mapping exists that could re-identify individuals. Still considered personal data under GDPR. Reduces risk but doesn't eliminate regulatory obligations.

**AI relevance:** many organizations mistakenly believe their training data is anonymized when it's actually only pseudonymized — and therefore still subject to privacy regulations. The distinction has significant compliance implications.

---

## Consent Management

The system and processes by which an organization obtains, records, and honors individuals' permissions for how their data is used. In AI contexts, consent management ensures that models train only on data that individuals have legally permitted to be used for that purpose.

**Why it's operationally hard:** consent must propagate in real time across every system that touches the data. If a user withdraws consent, that signal must flow through the data catalog, the feature store, the training pipeline, and any model already trained on that data — triggering retraining or model retirement if necessary. Batch-updated consent records create compliance windows.

---

## SECTION 8 — Integration Patterns & Architecture

New terms introduced in Component 03 — Access & Integration.

---

## Change Data Capture (CDC)

A technique that monitors a database's transaction log and captures every insert, update, and delete in near real-time, streaming those changes to downstream systems. Instead of copying entire tables on a schedule, CDC propagates only what changed. Latency: seconds. The bridge between operational databases and AI pipelines for use cases that need near-real-time data without full streaming infrastructure.

---

## Event Streaming

An integration pattern where every business action — a transaction, a click, a sensor reading, a status change — is published as an event to a streaming platform (Kafka, Pulsar) and consumed by downstream systems in real time. Latency: milliseconds. For autonomous agentic AI use cases, streaming is increasingly a production requirement, not an optimization.

---

## Data Virtualization

A layer that provides a unified query interface across distributed data sources without physically moving or copying the data. Queries execute against source systems in real time; the virtualization layer handles translation and federation. Useful where data can't or shouldn't be centralized due to regulatory, sovereignty, or cost constraints.

---

## Data Fabric

A unified logical layer that connects disparate physical data sources through metadata-driven integration, automation, and governance — without forcing all data into a single repository. Provides a single access point for all users and AI agents regardless of where data physically lives. AI-native by design: an agent queries the fabric; the fabric computes the answer from disparate sources in near real-time.

---

## Data Mesh

A decentralized organizational model where domain teams own and publish their own data as products, governed by federated standards. Data mesh distributes responsibility; data fabric centralizes intelligence. AI limitation: mesh governance assumes human discovery workflows — agents need programmatic, autonomous access that the mesh model wasn't designed to support directly.

---

## Semantic Layer

A business-friendly translation layer that maps raw database fields and tables to human-readable (and machine-readable) business concepts. Ensures that "revenue" means the same thing whether queried from finance, sales, or an AI agent. For agentic AI, the semantic layer is the machine-readable context that allows agents to understand what data means without human interpretation.

---

## Data Product

A curated, governed, and documented data asset published by a domain team for consumption by other teams or AI systems. A core concept of data mesh. Includes defined SLAs for freshness, quality, and availability — making it a reliable input for AI rather than a raw data dump.

---

## SECTION 11 — Security, Privacy & Compliance

New terms introduced in Component 06 — Security & Compliance.

---

## Data Poisoning

The deliberate insertion of corrupted, biased, or malicious data into a model's training, fine-tuning, retrieval pipeline, or agent tooling. The attack manipulates what the model learns, making the behavioral change persistent rather than temporary. Unlike prompt injection (which happens at runtime), data poisoning happens before runtime and embeds the malicious behavior into the model's weights. Classified by OWASP and NSA/CISA/FBI as a primary attack vector against AI systems in 2025.

---

## Model Inversion

An attack that attempts to reconstruct training data from a deployed model by repeatedly querying it and analyzing outputs. In some cases attackers can recover facial images, medical records, or financial data that appeared in training. A deployed model can be legally classified as personal data if it contains recoverable information about identifiable individuals, triggering GDPR and CCPA obligations.

---

## Membership Inference

An attack that determines whether a specific record was included in a model's training data — even without recovering the actual data. Knowing that a specific individual's data was used to train a model may itself constitute a privacy violation under applicable law.

---

## Differential Privacy

A mathematical technique that adds calibrated noise to training or query outputs so individual records cannot be identified, while preserving aggregate statistical properties. Provides formal, provable privacy guarantees. Used by Apple and Google for on-device ML. The gold standard for privacy-preserving machine learning.

---

## Federated Learning

A training architecture where models are trained across distributed data sources without centralizing the data. Each participant trains locally on their own data; only model updates (gradients) are shared, not raw data. The primary architecture for AI on regulated data (PHI, financial records) where data centralization is legally or practically prohibited.

---

## Synthetic Data

Artificially generated data that statistically mimics real data without containing actual personal information. Used to create training datasets free from privacy risk and erasure obligations. Quality depends on the fidelity of the generation process — poorly generated synthetic data can introduce statistical artifacts that degrade model performance.

---

## Data Minimization

Collecting and using only the data that is strictly necessary for the stated purpose. The simplest and most effective privacy control. Data that doesn't exist can't be breached, leaked, memorized by a model, or subject to erasure requests. A core principle under GDPR, CCPA, and most modern privacy frameworks.

---

## AI Supply Chain Attack

An attack targeting third-party components in the AI development pipeline — pre-trained foundation models, external datasets, open-source libraries, or external tool definitions used by agents. A single poisoned dataset used by a foundation model can propagate across thousands of downstream applications. Analogous to software supply chain attacks but harder to detect because model behavior is not deterministically inspectable.

---

## Purpose Limitation

A core privacy principle: data collected or consented to for one purpose cannot automatically be used for a different purpose. Critically, consent obtained for delivering a service does not extend to training an AI model on that same data. Organizations must establish separate legal bases or provide explicit notice before using personal data for AI training.

---

## Right to Erasure (AI Context)

The right of individuals under GDPR Article 17 and CCPA to request deletion of their personal data. In AI contexts, this creates a technically complex obligation: once personal data has influenced model weights during training, honoring an erasure request may require machine unlearning or full model retraining. The only reliable solution is prevention — not training on personal data subject to erasure in the first place.

---

## ABAC (Attribute-Based Access Control)

An access control model that extends RBAC with fine-grained conditions. Permissions are granted based on attributes of the user, the data, the resource, and the context of the request — not just the user's role. Example: this model can access this dataset IF the use case is approved AND the data is not flagged for erasure AND the requester has a valid research purpose. More expressive than RBAC; required for complex AI governance scenarios.

---

## Inference Data Leakage

The exposure of sensitive data sent to an AI system during inference — user queries, uploaded documents, context provided to agents — through vendor logging practices, model outputs, or third-party API data handling. Organizations using external LLM APIs must review terms for data retention and training use before sending any sensitive data.

---

## Zero Trust

A security model built on the principle of "never trust, always verify." No user, system, or agent is trusted by default — every access request must be authenticated and authorized regardless of whether it originates inside or outside the network perimeter. For AI systems, zero trust means every agent tool call, every data access, and every model query must be verified against current permissions at the moment of the request.

---

## SECTION 12 — Terms, Abbreviations & Acronyms

New terms and abbreviations identified across all documents in the knowledge base.

---

## GDPR (General Data Protection Regulation)

The European Union's primary data privacy law, enacted in 2018. Governs how organizations collect, store, process, and transfer personal data belonging to EU residents — regardless of where the organization is located. Establishes rights for data subjects including the right to access, correct, and erase their data. Fines reach up to €20M or 4% of global annual revenue for serious violations. GDPR enforcement reached €7.1B cumulative through 2025. In AI contexts, GDPR governs the use of personal data for model training, automated decision-making affecting individuals, and the technically complex right to erasure.

---

## CCPA (California Consumer Privacy Act)

California's consumer privacy law, enhanced by the CPRA (California Privacy Rights Act) in 2023. Grants California residents rights similar to GDPR — access, deletion, opt-out of sale — and adds Automated Decision-Making Technology (ADMT) requirements effective January 2026. Requires meaningful disclosure of decision-making logic for AI systems. Fines: \$2,663 per negligent violation, \$7,988 per intentional violation.

---

## HIPAA (Health Insurance Portability and Accountability Act)

US federal law governing the privacy and security of Protected Health Information (PHI). Any organization handling PHI in AI systems must comply with HIPAA's Privacy Rule (what can be shared) and Security Rule (how it must be protected). Business Associate Agreements (BAAs) are required with any AI vendor that processes PHI. Federated learning is the primary architectural strategy for AI on clinical data where data centralization creates HIPAA exposure.

---

## SLA (Service Level Agreement)

A formal commitment from a data producer (or service provider) to a consumer defining the minimum performance standards the data or service will meet. In data contracts, SLAs typically cover three dimensions: freshness (how recently the data was updated), availability (what percentage uptime is guaranteed), and latency (how quickly queries will return). SLAs make quality expectations enforceable — if the producer misses an SLA, the violation is detectable and triggers a governance response.

---

## KPI (Key Performance Indicator)

A quantitative metric used to measure progress toward a specific business or operational objective. In data quality governance, KPIs include quality scores, MTTD, MTTR, SLA compliance rates, and rule coverage percentages. Choosing the right KPIs is critical — organizations that track activity (checks run, tickets created) rather than outcomes (issues resolved, quality improving) lose visibility into whether governance is actually working.

---

## MTTD (Mean Time to Detect)

The average time between when a data quality issue is introduced and when it is detected by monitoring systems. A key governance KPI. Target for AI-critical assets: under 1 hour. Long MTTD means AI systems can operate on bad data for extended periods before anyone knows — compounding the damage with every decision made in the interim.

---

## MTTR (Mean Time to Resolve)

The average time between when a data quality issue is detected and when it is fully resolved. A companion KPI to MTTD. Targets: under 4 hours for critical issues, under 24 hours for major issues. MTTR reflects how effectively the remediation workflow functions — fast detection with slow resolution still means extended AI exposure to bad data.

---

## YAML

A human-readable data serialization format commonly used for configuration files, data contracts, and quality rule definitions. Stands for "YAML Ain't Markup Language." YAML's structure uses indentation rather than brackets or tags, making it readable to both humans and machines. Data contracts, dbt tests, and Soda quality checks are all commonly written in YAML.

---

## ODCS (Open Data Contract Standard)

An open standard for defining data contracts, maintained by the Linux Foundation's Bitol project. Defines a canonical YAML structure covering schema, quality rules, SLAs, ownership, semantics, and terms of use. Originally derived from a PayPal template, ODCS v3.0.0 was released in October 2024 with enhanced data quality support. The ODCS is the recommended foundation for organizations building data contract programs without vendor lock-in.

---

## GAN (Generative Adversarial Network)

A neural network architecture consisting of two competing networks: a generator that produces synthetic data, and a discriminator that tries to distinguish synthetic data from real data. The two networks train together — the generator improves until the discriminator can't reliably tell real from synthetic. GANs are one of the core methods for producing high-fidelity synthetic tabular data. CTGAN (Conditional Tabular GAN) is the most widely used GAN architecture specifically designed for enterprise tabular data.

---

## TSTR / TRTS (Synthetic Data Validation Methods)

Two complementary techniques for validating whether synthetic data is fit for model training:

- **TSTR (Train on Synthetic, Test on Real)** — train a model on synthetic data, evaluate it on a held-out real dataset. If synthetic data has high fidelity, performance should approach what you'd get training on real data.
- **TRTS (Train on Real, Test on Synthetic)** — the inverse. Confirms the synthetic data reflects the same patterns the real data contains.

Together, TSTR and TRTS provide the most direct measure of whether synthetic data is actually suitable for its intended AI use case.

---

## IAA (Inter-Annotator Agreement)

A statistical measure of how consistently different human annotators apply the same labels to the same examples. The primary quality metric for annotation programs. Low IAA indicates the task definition is unclear or annotators need more training — and that the labels being produced will contain high label noise. Should be measured before scaling any annotation program. Common metrics: Cohen's Kappa (two annotators), Fleiss' Kappa (multiple annotators), Krippendorff's Alpha (ordinal or complex scales).

---

## Cohen's Kappa (κ)

A statistical measure of inter-annotator agreement that corrects for the amount of agreement that would be expected by chance alone. A kappa of 1.0 means perfect agreement; 0 means agreement no better than chance; negative values mean worse than chance. Interpretation: κ above 0.8 is strong agreement; κ between 0.6 and 0.8 is moderate; κ below 0.6 indicates a task definition or training problem that must be fixed before scaling annotation.

---

## Krippendorff's Alpha

A statistical measure of inter-annotator agreement that generalizes across multiple annotators, different numbers of annotators per item, and different measurement scales (nominal, ordinal, interval, ratio). More flexible than Cohen's Kappa and preferred for complex annotation tasks where multiple annotators may label each item or where labels have a meaningful order.

---

## NLP (Natural Language Processing)

The field of AI focused on enabling computers to understand, interpret, and generate human language. NLP powers text classification, named entity recognition, sentiment analysis, machine translation, question answering, and large language models. Data quality is particularly critical for NLP: label noise in text annotation propagates into models that misclassify language at scale.

---

## NER (Named Entity Recognition)

An NLP task where a model identifies and classifies named entities in text — people, organizations, locations, dates, monetary values, and other domain-specific categories. A common annotation task in data labeling programs. NER models are foundational components of document AI, information extraction, and knowledge graph construction systems.

---

## CRM (Customer Relationship Management)

A system that manages an organization's interactions and relationships with customers and prospects — storing contact information, communication history, sales pipeline, and account data. In data readiness contexts, CRM systems are typically one of the primary sources for Customer MDM programs and a common source of PII that requires governance before entering AI pipelines.

---

## ERP (Enterprise Resource Planning)

An integrated system that manages core business processes — finance, procurement, supply chain, manufacturing, HR — in a unified platform. Common ERP systems include SAP, Oracle, and Microsoft Dynamics. In MDM contexts, ERP is often the authoritative source for supplier, product, and financial master data, and a key system to integrate when building golden records.

---

## Golden Record

The single, authoritative, most accurate and complete version of a master data entity — assembled by an MDM system from records across multiple source systems. Not the raw data from any one system, but the best possible reconstruction of truth built from all available sources according to defined survivorship rules. The golden record is the output of the MDM process and the input that AI systems should consume.

---

## Survivorship Rules

The logic that determines which attribute values populate a golden record when multiple source systems contain conflicting data for the same entity. For example: when the CRM says a customer's email is one value and the billing system says another, survivorship rules determine which one wins. Common survivorship strategies: source precedence (specific systems designated as authoritative for specific fields), most recent value, most complete value, frequency-based (most common value across sources), and confidence-weighted (ML-assigned scores determine the most reliable source).

---

## ADAS (Advanced Driver Assistance Systems)

Vehicle safety technology that uses sensors, cameras, and AI to assist drivers — lane departure warnings, automatic emergency braking, adaptive cruise control. A major application area for computer vision AI and a common use case for specialized video annotation and labeling programs. ADAS models require extremely high-quality, precisely labeled training data because errors can have safety consequences.

---

## MAL (Model-Assisted Labeling)

An annotation workflow where a pre-trained ML model generates initial draft labels for a dataset, which human annotators then review, correct, and approve. Significantly reduces annotation time compared to labeling from scratch — enterprise teams report up to 60% reduction in annotation time for image classification tasks. The quality of the draft labels depends on how closely the pre-trained model's domain matches the annotation task.

---

## SPC (Statistical Process Control)

A method of quality control that uses statistical methods to monitor and control a process. In data quality contexts, SPC applies control charts and statistical tests to data metrics — tracking whether metrics like null rates, value distributions, or row counts are within normal operating bounds. When a metric crosses a control limit, it signals a data quality issue requiring investigation. Particularly useful for detecting gradual drift in data pipelines.

---

## SMOTE (Synthetic Minority Oversampling Technique)

A technique for addressing class imbalance in training datasets by generating synthetic examples of the minority class. Rather than simply duplicating existing minority examples (which can cause overfitting), SMOTE creates new synthetic examples by interpolating between existing minority class examples in feature space. Commonly used when rare events (fraud, defects, rare medical conditions) are underrepresented in training data.

---

## SHAP (SHapley Additive exPlanations)

A method for explaining individual model predictions by calculating each feature's contribution to a specific output. Based on Shapley values from cooperative game theory. SHAP answers: for this specific prediction, how much did each input feature push the output higher or lower? Widely used for post-hoc explainability of complex models (gradient boosting, neural networks) that are not inherently interpretable.

---

## LIME (Local Interpretable Model-Agnostic Explanations)

A method for explaining individual model predictions by approximating the model locally with a simpler, interpretable model. LIME perturbs the input slightly, observes how the prediction changes, and fits a linear model to those perturbations to explain what features drove the prediction. Model-agnostic — works with any ML model regardless of architecture.

---

## CAGR (Compound Annual Growth Rate)

The rate at which a quantity grows from one value to another over a multi-year period, expressed as an annual percentage, assuming compounding. Used throughout this knowledge base to describe market growth rates. Formula: (End Value / Start Value)\^(1/Years) - 1. A CAGR of 17% means a market is growing at a rate that, compounded annually, would take it from its starting size to its ending size over the stated period.

---

## ICP (Ideal Customer Profile)

A description of the type of company or customer that is the best fit for an organization's product or service — typically defined by firmographic attributes (industry, company size, revenue, geography) and behavioral signals (usage patterns, buying behavior). Commonly used in sales and marketing AI use cases: lead scoring models, next-best-action systems, and outreach personalization tools all depend on a well-defined ICP to produce relevant outputs.

---

## DBA (Database Administrator)

A technical role responsible for the installation, configuration, performance, security, and maintenance of database systems. In data governance contexts, DBAs often serve as Data Custodians — implementing the access controls, backup policies, and security configurations defined by data owners and stewards. Not to be confused with the business degree abbreviation.

---

## YAML (see above) \| git

**git** — a distributed version control system that tracks changes to files over time. Widely used in software engineering; increasingly adopted for data engineering and AI workflows. In the context of data contracts and quality rules, "version-controlled like code" means stored in git: every change is tracked, attributed to an author, reviewable before merging, and reversible. Git enables the same accountability and auditability for data definitions that software teams apply to application code.
