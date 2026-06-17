---
type: Concept
title: Technology Architecture Framework
description: What the AI platform layer owns — tooling standardization, API governance, model selection, and build vs. buy vs. partner decisions.
tags: [ai-platform, architecture, model-selection, mlops, api-governance]
timestamp: "2026-06-17"
status: published
---

## Why AI Platform Architecture Matters Now

Most enterprises did not set out to build an AI platform. They set out to solve individual problems. A customer service team integrated a chatbot. A product team added a copilot. An engineer connected a business process to the OpenAI API over a weekend. Each experiment was rational in isolation. Collectively, they produced something no one intended: a sprawl of point solutions, redundant subscriptions, disconnected embedding pipelines, and business units spinning up their own models against their own API keys with no central visibility into cost, performance, or risk.

This is not a hypothetical. McKinsey's 2025 State of AI report found that 78% of organizations are using AI in at least one business function — but only a minority have consolidated their AI infrastructure into a coherent platform layer. The rest are managing dozens of separate AI relationships, each with its own billing, its own data handling posture, and its own failure modes. Gartner estimates that unmanaged AI API spend is now a material line item at enterprises of all sizes, with shadow AI subscriptions accounting for a meaningful and growing share of cloud spending that does not appear in IT budgets.

The cost of point-solution sprawl is not only financial. It is architectural. An enterprise cannot audit what it cannot see, cannot govern what it did not provision, and cannot optimize what it has no unified view of. When every team routes its prompts through a different API key, there is no way to aggregate cost, enforce policy, or catch a runaway agent before the invoice arrives. When every team selects its own models, there is no shared evaluation, no compliance review, and no mechanism to retire a model that turns out to be unsuitable.

> **78% of organizations** now use AI in at least one business function *(McKinsey, State of AI, 2025)*, yet only **35% of enterprises** report having a centralized AI infrastructure function with defined ownership of API access, model selection, and cost governance *(Gartner, AI Infrastructure Survey, 2025)*

This track defines the platform layer that makes everything else work. [Track 02 (AI Governance & Risk)](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md) sets policy — which models are approved, what data handling is permissible, what human review is required. Track 03 (Data Readiness) manages the inputs — data quality, pipelines, lineage. Track 04 provides the shared engineering layer that makes both operational: the API gateway through which governed models are accessed, the model registry that enforces compliance classifications, the observability infrastructure that gives governance and data teams visibility into what is actually running.

Without the platform layer, governance is a document and data readiness is a project. With it, both become enforceable, auditable, and improvable over time.

---

## What the AI Platform Layer Owns

The AI platform layer is not the same as the ML engineering team that builds models, and it is not the same as the IT infrastructure team that manages compute. It is the function that owns the shared services on which all AI development in the enterprise depends — the APIs, registries, orchestration infrastructure, and observability tooling that individual teams build on rather than rebuild for themselves.

The scope of the AI platform layer covers five domains:

**API gateway and cost governance.** The platform layer owns the single controlled access point through which teams reach external model APIs — OpenAI, Anthropic, Google Gemini, Cohere, and open-source inference endpoints. Centralized access enables unified cost visibility (spending by team, by use case, by model), rate limiting (preventing a runaway agent or an overbudget experiment from consuming the organization's API allocation), and audit logging (a complete record of what prompts went to which models and when, which is required by both governance frameworks and, increasingly, regulation). Without centralization at the API layer, none of these controls are possible. See [API Governance and Cost Control](#api-governance-and-cost-control) for implementation patterns.

**Model registry and selection.** The platform layer maintains a shared catalog of approved models — the set of models that have been evaluated, classified for compliance purposes, and approved for use in production. Each registry entry captures the model's capabilities, benchmark performance on task types relevant to the organization, cost profile, data residency and training data provenance, EU AI Act classification, and the use cases it is approved for. The registry is the operational bridge between governance policy and engineering practice: governance approves which models are permissible; the registry makes those decisions accessible to teams at the point of selection.

**Orchestration and agent infrastructure.** When teams build LLM-powered applications — chains, agents, retrieval-augmented generation pipelines, multi-step workflows — they need shared infrastructure to do it on. The platform layer owns the shared orchestration runtime, prompt management system, caching layer, and agent execution environment. Shared orchestration infrastructure means teams are not re-implementing the same patterns independently, and it means the platform team has visibility into how the infrastructure is being used. See [the tooling landscape overview](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/03-tooling-landscape.md) for the current state of the framework and runtime ecosystem.

**Developer enablement.** The best platform is one that makes the right thing the easy thing. Developer enablement means SDKs, internal APIs, prompt templates, starter kits, and integration patterns that let product and engineering teams build on approved infrastructure without re-solving solved problems. A team integrating a RAG pipeline should be starting from a working template, not a blank file. A team choosing a model should be consulting a registry with evaluations already done, not conducting their own evaluation from scratch.

**Observability and cost reporting.** The platform layer owns the unified dashboard that shows API spend by team and model, latency distributions by use case, error rates, and cache hit rates. Observability is not optional — it is the mechanism by which every other platform function is validated. Cost reporting is the primary tool for accountability and for identifying where platform investment (caching, batching, model substitution) pays off.

---

## Model Selection and Evaluation

Choosing a model is not a one-time decision, and it is not a vendor preference. It is an engineering decision made against a specific set of requirements, and it should be made with evidence.

The relevant dimensions for model selection vary by use case, but the framework is consistent:

**Capability.** Does the model perform well enough on the specific task type? Benchmark scores on MMLU or HumanEval are useful signals but rarely sufficient — they measure performance on standardized test sets, not on the organization's actual prompts. Capability evaluation must use a representative sample of real production prompts (or a representative proxy), with human evaluation or automated evaluation against ground-truth outputs. A model that scores highest on general benchmarks may underperform on the organization's specific domain vocabulary, document formats, or reasoning requirements.

**Cost.** Per-token or per-call costs must be evaluated at expected volume, not at prototype scale. A model that is affordable at 10,000 calls per day becomes a significant budget item at 10 million. Cost modeling should include input tokens, output tokens, caching discounts, and the cost of any fine-tuning or retrieval infrastructure. The cheapest capable model for a given task is usually the right model, but "cheapest" must be evaluated over the actual usage profile, not the pricing page.

**Latency.** Interactive use cases (copilots, chatbots, real-time assistance tools) have hard latency requirements — users notice and abandon experiences with response times above 2–3 seconds for most prompt lengths. Batch processing use cases (document processing, nightly enrichment pipelines) have effectively no latency constraint. Model selection must account for this: the fastest model is not always the most capable, and the most capable model is not always fast enough.

**Compliance.** Data residency requirements (does processed data leave the EU?), training data provenance (was the model trained on data that creates IP or privacy exposure?), and EU AI Act classification (is this a high-risk AI system under Annex III?) all constrain the set of permissible models. These are not post-hoc considerations — they are first-pass filters that determine which models are eligible before capability evaluation begins.

**Vendor risk.** Model providers vary substantially in their contractual posture on model change notification, data handling, SLA commitments, and lock-in exposure. A model that is excellent today and changes materially without notice creates a governance and performance risk. Vendor risk assessment for model selection follows the same framework as [vendor risk in AI governance](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md) — contractual protections, notification rights, and auditability all matter.

**The build vs. fine-tune vs. API decision.** Most organizations should start with foundation model APIs and move toward customization only when the evidence supports it. The decision logic:

- Use a **foundation model API** when the task is within the model's general capability, latency and cost are acceptable at target volume, and the use case does not require knowledge or behavior that cannot be conveyed in the prompt or retrieved via RAG. This is the right default for most enterprise AI applications.
- Consider **fine-tuning** when a task type requires consistent formatting, tone, or domain-specific behavior that cannot be reliably achieved through prompting; when the volume is high enough that fine-tuned efficiency gains pay for the tuning cost; or when prompting a large model is too slow or expensive for the use case. Fine-tuning on task structure and format is commonly worthwhile; fine-tuning to inject knowledge (as opposed to using RAG) is usually not.
- Consider **open-source or self-hosted models** when data must not leave the enterprise perimeter, when volume is so high that API costs exceed the cost of running infrastructure, when the use case requires a model size that runs efficiently on commodity hardware, or when the enterprise has a genuine need to inspect and modify model weights.
- **Build a specialized model** only when the enterprise has a truly distinctive data asset or task structure that no available model — fine-tuned or otherwise — can address, and when the organization has the ML engineering capability to sustain a model development program. This is rare and expensive; most "we should build our own" instincts are better served by fine-tuning or retrieval augmentation.

Document every model selection decision: the use case, the evaluation set, the models evaluated, the scores on each dimension, and the rationale for the choice made. Model selection documentation is both a governance artifact and an institutional asset — it prevents the same evaluation from being repeated in six months.

---

## API Governance and Cost Control

Without centralized API governance, costs balloon invisibly. The bill arrives at the end of the month and no one can explain which team, which application, or which experiment generated which portion of the spend. By the time an explanation is assembled, another month has passed. This is the default state of enterprises that allow direct API access by individual teams.

The alternative is an API gateway pattern: a single controlled access point that all AI API traffic routes through before reaching the upstream model provider. The gateway handles authentication (teams get gateway credentials, not provider credentials), logging (every request is recorded with team, use case, model, token counts, and cost), budget enforcement (spending limits by team and use case, with alerts before limits are reached), and rate limiting (preventing runaway agents or misfired loops from consuming the quota).

Implementation patterns for cost control:

**Prompt caching.** Both Anthropic and OpenAI offer prompt caching at significant discounts — Anthropic's cache reads are priced at 10% of base input token cost, and OpenAI's cached prompt tokens are charged at 50% of standard input pricing. For applications with large, stable system prompts (long instruction sets, reference documents, few-shot examples), caching the static prefix can reduce input token costs by 60–90% on repeated calls. The platform layer should implement caching by default for all prompts with static prefixes above a threshold length, rather than leaving caching decisions to individual application teams.

**Model tiering and routing.** Not every query requires the most capable (and most expensive) model. A routing layer that sends simple, well-defined queries to a smaller, cheaper model and reserves the frontier model for complex or ambiguous queries can reduce cost substantially with minimal quality impact. The platform layer owns the routing logic; individual teams define the complexity threshold for their use case.

**Batch processing.** Anthropic and OpenAI both offer batch APIs at significant per-token discounts (50% for Anthropic's Batch API, 50% for OpenAI's Batch API) for non-real-time workloads. Document processing, nightly enrichment, bulk classification, and evaluation runs are all candidates for batch processing. The platform layer should expose a batch queue as a first-class service, making it trivially easy for teams to route eligible workloads to the batch endpoint.

**Usage budgets and alerts.** Every team and every use case should have a defined monthly budget, with alerts at 70% and 90% of budget before the limit is reached. The platform layer owns the budget tracking and alerting infrastructure. Alerts go to both the team lead and the platform team — cost overruns are a signal of either a runaway process or a use case that has scaled faster than anticipated and needs infrastructure review.

**Request logging for audit.** Every request through the API gateway must be logged: timestamp, team, use case, model, input tokens, output tokens, cost, response latency, and whether the request hit cache. Logs serve three purposes: cost attribution (accurate billing back to teams), compliance audit (proof that governed models were used for governed use cases), and performance analysis (identifying which use cases are bottlenecked on latency or where cache hit rates could be improved).

---

## Build vs. Buy vs. Partner

The most consequential platform architecture decision is not which model to use or which orchestration framework to adopt. It is the meta-decision of what to build, what to buy, and what to partner for — applied layer by layer, not answered once for the whole platform.

Most organizations get this wrong by defaulting to one answer. "We buy everything" leaves the enterprise dependent on off-the-shelf solutions that encode other organizations' integration assumptions and cannot be tailored. "We build everything" consumes engineering capacity on infrastructure that commodity vendors build better and faster, and distracts from the institutional knowledge that actually differentiates the enterprise.

The right framework is tiered:

| Layer | Decision | Rationale | Examples |
|---|---|---|---|
| **Commodity infrastructure** | Buy or use managed services | No differentiation in owning this; off-the-shelf solutions are better-maintained and more capable than anything an enterprise would build | Foundation model APIs, vector databases (Pinecone, Weaviate, pgvector), embedding services, managed inference (Vertex AI, Bedrock, Azure OpenAI Service) |
| **Integration and orchestration** | Build integration logic on top of bought/open-source components; own the integration patterns | The glue between commodity components is specific to the enterprise's data model, process, and security requirements; own this layer | Internal API gateway configuration, routing logic, prompt management system, RAG pipeline architecture, cost attribution logic |
| **Strategic capability** | Build what encodes institutional knowledge; own and maintain | This is what actually differentiates the enterprise — the prompts, fine-tuned behaviors, and retrieval corpora that reflect institutional expertise | Fine-tuned models trained on proprietary data, prompt libraries encoding domain expertise, evaluation sets built from institutional knowledge, custom agents that automate proprietary workflows |

The practical implication: invest in buying robust commodity infrastructure, build opinionated integration and orchestration on top of it, and apply genuine engineering investment to strategic capability. A large language model is not a strategic capability; the prompts and retrieval corpora that make it behave like a domain expert at your organization usually are.

See the [practitioner guide to designing an AI platform function](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/04-practitioner-guide-designing-an-ai-platform-function.md) for worked examples of applying this framework in financial services, healthcare, and industrial settings.

---

## Platform Governance and the Build-Out Sequence

Order matters. Organizations that try to build the full AI platform at once produce a partially-complete platform with no component working well enough to drive adoption. The sequence below is not the only viable order, but it reflects where most enterprises get early value and where dependencies are real.

**Stage 1: Centralized API access and cost visibility.** Stand up the API gateway first. This produces immediate value (cost visibility, rate limiting, audit logging) and creates the foundation for every subsequent stage. It is also the easiest stage to justify: the cost savings from preventing runaway experiments and enabling caching typically pay for the gateway infrastructure within one or two billing cycles. Every model API call in the organization should route through the gateway before any other platform work begins.

**Stage 2: Model registry and evaluation capability.** Build a shared catalog of approved models with their capability classifications and compliance status. Stand up a lightweight evaluation infrastructure — a harness for running representative prompts against candidate models and comparing outputs. The registry does not need to be sophisticated; a well-maintained shared document is better than a complex system no one updates. The evaluation harness does need to be repeatable — model selection decisions should be reproducible, not dependent on individual memory.

**Stage 3: Shared orchestration infrastructure.** Once teams have an approved set of models to work with and a gateway to access them through, build the shared orchestration layer — the prompt management system, caching layer, and agent runtime that teams build on. Do not build this until Stage 1 and Stage 2 are stable; teams building on unstable infrastructure produce systems that fail in ways that are hard to attribute.

**Stage 4: Developer enablement.** Once the platform is stable, invest in making it easy to use: documentation, starter kits, reference implementations, office hours, and onboarding support. Developer enablement is what converts a platform into an organization-wide capability — without it, the platform is used only by the teams that helped build it.

**Avoiding premature standardization.** Do not mandate a single orchestration framework organization-wide before the use cases are understood. The right orchestration pattern for a customer service chatbot is different from the right pattern for a document processing pipeline or a multi-step coding agent. Let early use cases inform platform decisions rather than locking the platform before the use cases are known. The platform team should hold off on hard framework mandates for at least the first six to twelve months of production operation.

**Platform governance.** The AI platform is shared infrastructure. Changes to it — new models in the registry, changes to the gateway configuration, updates to the orchestration framework, pricing changes in the cost allocation model — affect every team that depends on it. Platform governance defines how changes are proposed, tested, communicated, and rolled back if needed. At minimum: a change log accessible to all consuming teams, advance notice (not same-day) for changes that affect API contracts or cost attribution, and a rollback procedure for any change to the gateway or routing configuration.

---

## Common Failure Modes

**Tool sprawl.** Each team picks its own AI stack. One team uses LangChain, another LlamaIndex, a third has built custom orchestration. Each team manages its own API key, its own embedding pipeline, its own vector store. There is no shared cost visibility, no shared model registry, and no mechanism to enforce governance policy. Sprawl compounds over time — the more independently each team operates, the harder it is to consolidate, and the more expensive any consolidation becomes. The antidote is establishing the API gateway and model registry early, before sprawl becomes entrenched.

**Premature platform lock-in.** The platform team selects one orchestration framework and mandates it across the organization before production use cases are established. Six months later, the framework turns out to be poorly suited to the most important use case class, or the vendor pivots, or a clearly superior alternative emerges. Unwinding an org-wide framework mandate is expensive and disruptive. Platform standardization decisions should be made deliberately and late — after enough production experience to understand the actual requirements.

**Shadow AI infrastructure.** Business units or engineers route around the approved platform because it is too slow, too restricted, or too bureaucratic. They access model APIs directly, spin up their own vector databases, or deploy their own agent runtimes. Shadow AI infrastructure is a signal that the platform is not meeting teams' needs — it should be treated as feedback, not as a compliance violation. The response is to make the platform faster and easier to use, not to add more restrictions that get routed around even more creatively.

**Governance theater.** A shared API gateway exists, a model registry has been created, and the documentation is comprehensive. But no one checks the cost attribution reports. The model registry has not been updated in four months. The gateway logs are stored but never reviewed. The evaluation process is documented but teams skip it when they are under time pressure. Governance theater in platform architecture has the same root cause as governance theater everywhere else: the platform team is measured on shipping the platform, not on the platform being used and maintained. Active governance requires active maintenance — someone must own the registry, review the cost reports, and follow up when teams bypass the evaluation process.

---

## Platform Architecture Checklist

- [ ] All AI API traffic (external model providers) routes through a centralized API gateway — no team-managed API keys in production
- [ ] Cost attribution is active: API spend is tracked by team, use case, and model, and reported at least monthly
- [ ] Spending budgets and alerts are configured for every team and use case, with alerts before limits are reached
- [ ] A model registry exists, is actively maintained, and covers all models approved for production use including compliance classifications and EU AI Act tier
- [ ] Prompt caching is enabled for all prompts with large static prefixes; batch processing is used for eligible non-real-time workloads
- [ ] A model evaluation harness is in place; model selection decisions are documented with the evaluation set, scores, and rationale
- [ ] Shared orchestration infrastructure is available for teams to build on, with reference implementations and starter kits
- [ ] Developer documentation covers how to access the API gateway, use the model registry, deploy on shared orchestration, and submit model evaluation requests
- [ ] An observability dashboard is active showing API spend, latency distributions, error rates, and cache hit rates across the platform
- [ ] A platform change management process is defined: advance notice to consuming teams, change log, and rollback procedure

Assess your organization's current platform maturity against the [platform maturity scoring assessment](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/05-assessment-platform-maturity-scoring.md). For the governance framework that defines policy the platform must enforce, see [Track 02, AI Governance Framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md).

---

## Sources

- McKinsey & Company — *The State of AI* — 2025
- Gartner — *AI Infrastructure and Platform Survey* — 2025
- Anthropic — *Prompt Caching Documentation* — 2025 (docs.anthropic.com/en/docs/build-with-claude/prompt-caching)
- OpenAI — *Prompt Caching and Batch API Documentation* — 2025 (platform.openai.com/docs/guides/prompt-caching)
- Gartner — *Build, Buy, or Partner: Evaluating AI Platform Strategies for the Enterprise* — 2024
- McKinsey & Company — *Scaling AI in the Enterprise: Infrastructure, Governance, and Value Capture* — 2025
- NIST — *AI Risk Management Framework (AI RMF 1.0)* — January 2023
- Linux Foundation AI & Data — *State of Enterprise Open Source AI* — 2025
