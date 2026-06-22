---
type: Playbook
title: "Practitioner Guide: Designing an AI Platform Function"
description: "How to design an AI platform function, including vendor evaluation, API cost governance, developer enablement, and integration patterns."
tags: [ai-platform, vendor-evaluation, integration, practitioner-guide, mlops]
timestamp: "2026-06-18"
---

## What this guide is for

This guide is written for the platform engineer, AI lead, or CTO/VP Engineering handed a mandate that sounds like "build the AI platform." That mandate shows up in different forms: standardize the chaos of team-by-team API integrations, give developers a better way to work with models, establish cost control over AI spend that nobody currently has visibility into, or simply "make sure we're doing AI right." All of those mandates converge on the same underlying work: turning a collection of independent experiments and ad hoc integrations into shared, governed infrastructure.

This guide assumes some AI is already in production or actively being built. That is a safe assumption — by late 2025, 88% of organizations reported using AI in at least one business function ([McKinsey, 2025](#ev-mckinsey-state-of-ai-2025-adoption)). The question is not whether your organization should use AI; that decision has already been made, often by teams who didn't wait for infrastructure to be ready. The question is how to build a platform function that makes AI use safer, cheaper, and more productive, without creating a bottleneck that slows down every team that wants to do something new. The stakes are real: roughly 42% of companies abandoned most of their AI initiatives in 2025, up from 17% the year before ([S&P Global Market Intelligence, 2025](#ev-sp-global-vote-2025-abandoned-ai-initiatives)), and the difference between the projects that stick and the ones that get scrapped is usually infrastructure and integration, not model quality.

What this guide produces is a platform function with real capability in 90 to 120 days: centralized API access with cost attribution, shared infrastructure that teams actually use, developer documentation that answers the questions people are already asking, and a model evaluation process that makes "which model should we use?" a solvable problem rather than a recurring debate. Maturity beyond that 90-day baseline is ongoing. This guide covers the first phase of it.

---

## Before you start: what problem are you solving?

The most common mistake in AI platform work is building infrastructure before understanding what the infrastructure must serve. Teams build a model registry because model registries are best practice, stand up a vector database because they've heard about RAG, and integrate an orchestration framework because an engineering blog post made it look essential — and then discover that none of the actual use cases in their organization require any of those things yet, while the authentication and cost attribution problems that are causing real pain every day remain unsolved.

The antidote is a two-week audit conducted before any platform architecture decisions are made. The audit reveals what is actually happening with AI in the organization: which teams are using it, what they're building, what is breaking, and what the real requirements for shared infrastructure are.

### The shadow AI audit

Most organizations have significantly more AI use in production than their official inventories reflect. Teams build prototypes that quietly become production systems. Individual contributors sign up for API keys on personal credit cards. Vendor SaaS products ship AI features enabled by default. The scale is well documented: 78% of AI users report bringing their own AI tools to work ([Microsoft & LinkedIn, 2024](#ev-microsoft-work-trend-2024-byoai)), and shadow AI is now a measurable security exposure — one in five breached organizations attributed the breach in part to shadow AI, which added roughly $670,000 to the average breach cost ([IBM, 2025](#ev-ibm-cost-of-breach-2025-shadow-ai)). Before you can govern or support AI use, you need to find it all.

Conduct the audit through three channels: an engineering survey (low barrier; ask people to self-report — most will cooperate if you frame it as gathering information to help them, not to restrict them), a network-level review of DNS queries and egress traffic patterns (catches external AI API calls that weren't disclosed), and a vendor contract review (identify which SaaS products include AI capabilities, and whether those capabilities are enabled). The goal is a complete picture of AI use, not a punitive exercise. Make that framing explicit.

### Mapping API spend by team

Once you have a list of AI systems and teams, map the spend. This is often the first time anyone has a consolidated view of what AI is actually costing the organization — and that gap is the norm, not the exception: as of 2025, only 63% of organizations were tracking or managing AI spend at all, up from 31% a year earlier ([FinOps Foundation, 2025](#ev-finops-foundation-state-of-finops-2025-tracking-spend)). Common findings: one or two teams account for a disproportionate share of spend with no awareness of the cost, duplicate API subscriptions to the same providers under different payment methods, and significant spend on high-cost models for use cases that would be adequately served by lower-cost alternatives.

Collect invoices, expense reports, and any corporate card charges from AI vendors. Build a simple spreadsheet: team, provider, monthly spend, use case, model used. This artifact drives the cost governance design in Phase 1.

### Identifying integration pain points

Interview five to ten engineers who are actively building AI-powered features. Ask them what is slowing them down. The answers cluster predictably: getting access to models takes too long, there is no documentation for which model to use for which task, authentication is complex and inconsistently implemented across teams, there is no shared way to handle retries and rate limits, and nobody knows how to debug prompt behavior in production. These are the integration pain points the platform must address first — not the architectural concerns that appear in vendor whitepapers.

### Cataloguing existing tools

Inventory what is already in place: which AI vendors have active contracts, what internal tooling exists (prompt management spreadsheets, shared utility functions, internal libraries), and whether any team has already built something that could be shared. Avoid rebuilding what already exists. Existing work that is well-designed can become platform components; existing work that is poorly designed at least tells you what problems teams have been struggling with.

**Output of the audit:** a platform requirements brief that covers the use cases the platform must serve in priority order, the integration pain points that need to be solved first, the cost visibility gaps that need to be addressed, and the existing tools and contracts that the platform should build on or replace. Bring this brief to every subsequent architecture conversation. Every platform decision should trace back to a requirement in the brief.

---

## Phase 1: Establish the foundation (weeks 1–6)

The goal of Phase 1 is a minimum viable platform that delivers immediate value and creates the infrastructure every subsequent capability builds on. The emphasis is on infrastructure that is live and in use — not on infrastructure that is perfectly designed but still in staging.

### Set up a centralized API gateway

The single highest-leverage action in early platform work is routing all AI API calls through a centralized gateway. LiteLLM is the most common open-source choice; it provides a unified API surface across providers (OpenAI, Anthropic, Google, and others), built-in request logging, cost attribution by team or project, and retry handling. Managed alternatives exist from cloud providers (Azure API Management's AI gateway capabilities, AWS Bedrock with reference gateway patterns) and AI-native vendors (Portkey, Helicone) if operational overhead is a constraint.

Turn on logging and cost attribution on day one. Do not wait until the gateway is fully hardened or until every team is using it before turning on logging — the data from early usage is what reveals the next set of requirements. Every API call through the gateway should emit: timestamp, requesting team or application, model name, token counts (input and output), latency, and success or failure status. This logging infrastructure is what makes every subsequent governance and cost management conversation possible.

Migration of existing teams onto the gateway should be a Phase 1 deliverable, not a later step. Run the migration team by team over the first four to six weeks. It requires a code change on each team's side (replacing direct provider API calls with the gateway's equivalent endpoint) and is typically a half-day of engineering work per integration. The migration pays for itself in cost visibility within the first billing cycle.

### Define an approved model list

Publish a starting list of approved models and the recommended use case for each. The list does not need to be comprehensive — it needs to be clear and opinionated. Something like: one recommended model for general text generation tasks, one for code generation, one for embeddings, one for tasks requiring long context, and one low-cost option for high-volume classification or routing tasks. Include the rationale for each recommendation so teams can make informed decisions about when to deviate. Plan for the list to span providers — enterprise LLM spend is now split across Anthropic, OpenAI, and Google rather than concentrated in one vendor ([Menlo Ventures, 2025](#ev-menlo-ventures-state-genai-2025-llm-spend-share)), and a single-provider approved list ages quickly.

The approved model list serves two purposes. It reduces the decision overhead for teams (most teams want guidance, not unlimited choice), and it creates a foundation for cost governance (teams using models not on the list need a reason). The list will evolve; the process for updating it is covered in Phase 3.

### Establish cost budgets and alerts

With the gateway in place and spend data flowing, set initial budgets by team. In the absence of usage history, start with conservative estimates derived from the audit data and adjust within the first month. The goal at this stage is not optimized cost allocation — it is visibility and early-warning alerts before costs become a problem. Configure alerts at 70% and 90% of budget so teams have time to respond before hitting limits. <!-- noev: budget-alert thresholds are an implementation recommendation, not a sourced statistic -->

Budget conversations are most productive when framed around use cases rather than dollar amounts. "How many requests per day does your use case generate, and at what average token count?" is a more productive question than "how much do you expect to spend?" Teams rarely know their expected spend; they often do know their expected usage patterns.

### Create basic developer documentation

The most common failure mode in early platform work is building infrastructure and then assuming developers will figure out how to use it. They won't, or they will figure it out at significant individual cost that gets repeated across teams. Documentation is platform infrastructure.

The minimum documentation set for Phase 1: how to get access (authentication, credential management, who to contact), which model to use for which type of task (with explicit guidance, not just a model list), a quickstart code example in the two or three languages most common in your stack, and where to ask questions. This does not need to be elaborate. A well-organized internal wiki page that answers those four questions is sufficient. The signal that documentation is working is that engineers stop asking each other the same questions in Slack.

### Set up a model registry

A model registry is a maintained inventory of models approved for use in the organization, with metadata about each: provider, version, capabilities, cost per token, context window size, data handling terms relevant to your compliance posture, and any restrictions on use cases. The model registry feeds the governance model inventory and is the authoritative source for the approved model list.

In Phase 1, the registry can be as simple as a maintained table in your internal documentation. The discipline is in keeping it current — when a model version is deprecated, when a new model is approved, when pricing changes. Assign explicit ownership for registry maintenance. This matters more than it sounds: provider model deprecations are routine and can be abrupt (OpenAI, for example, gave preview-model deprecations as little as two weeks' notice and hard-sunset its first-generation GPT-3 models on a fixed date), so a registry that nobody owns becomes dangerously stale.

**Phase 1 deliverable:** The API gateway is live. Every team's AI API calls are routed through it. Cost attribution by team is operational. An approved model list is published. Basic developer documentation exists. The model registry has initial entries for each approved model.

---

## Phase 2: Build shared infrastructure (weeks 7–12)

With the gateway live and cost visibility established, Phase 2 adds shared infrastructure that reduces duplicated effort across teams and establishes the observability foundation for ongoing operations.

### Shared embedding infrastructure

Embeddings — vector representations of text used in semantic search, retrieval-augmented generation, and clustering — are almost universally useful across AI use cases, and almost universally built redundantly when teams are working independently. Every team that builds a RAG pipeline builds its own embedding service. The code is nearly identical; the cost and maintenance overhead is multiplied by the number of teams.

Stand up a shared embedding service: a single endpoint that accepts text and returns embeddings using the organization's approved embedding model. The service should handle batching (aggregating multiple requests for efficiency), caching for repeated inputs (embeddings for the same text are deterministic; caching avoids redundant API calls), and logging consistent with the rest of the platform. Once the service is in place, point teams at it rather than at direct embedding API calls.

### Vector store provisioning

Most early-stage RAG use cases do not require a dedicated vector database. If your organization already runs PostgreSQL at reasonable scale, pgvector (an open-source extension) covers a wide range of retrieval use cases and eliminates the operational overhead of a separate vector database system. Evaluate this option honestly before provisioning a dedicated vector store — the operational cost of pgvector is near zero if Postgres is already managed, while a dedicated vector database adds a new system to operate, monitor, and pay for.

Dedicated vector databases (Pinecone, Weaviate, Qdrant, Milvus, and others) are appropriate when: retrieval performance at scale is a hard requirement, multi-tenancy or isolation between use cases is needed, or the use case requires capabilities — approximate nearest neighbor at very high query-per-second rates, built-in hybrid search and filtering — that pgvector does not efficiently support. Make this an architecture decision based on actual requirements, not on the assumption that "serious" RAG requires a "serious" vector database.

### Reference architecture for common patterns

One of the highest-leverage outputs of a platform function is a set of reference architectures that teams can fork rather than design from scratch. Three patterns cover the majority of use cases:

A **RAG pipeline reference**: document ingestion, chunking, embedding, and storage; query transformation, retrieval, reranking, and generation. Include the recommended library or framework for each stage, sample code, and explicit notes on the failure modes — stale retrieval indexes, chunk size tradeoffs, retrieval quality evaluation.

An **agent orchestration reference**: how to design a single-agent workflow with tool access, how to structure multi-step tasks, how to handle tool call failures and retries, and when human escalation is required. Include the approved tool access patterns and the logging requirements for agentic workflows.

A **structured output pattern**: how to reliably extract structured data from model outputs — validated JSON schemas, retry logic for malformed outputs, and how to evaluate extraction quality. This pattern appears in a surprising proportion of enterprise AI use cases.

Reference architectures are not mandates. Teams can deviate when their use case requires it. The reference exists to reduce the cost of starting and to concentrate hard-won lessons about what doesn't work in one place rather than re-learning them per team.

### LLM observability

Observability for AI systems is not the same as observability for conventional software. The standard metrics — CPU, memory, request latency, error rate — are necessary but insufficient. AI-specific observability includes: token counts per request (input and output separately, since they price differently and have different implications for cost optimization), model version in use (important when a provider updates a model without changing the name), prompt and completion logging for debugging, and per-use-case quality metrics (which are use case specific and require explicit design — there is no universal AI quality metric).

Stand up an LLM observability stack in Phase 2. Options range from open-source (Langfuse, Helicone, and similar) to commercial (Braintrust, LangSmith). The minimum requirements: every request through the gateway produces a structured log entry with the metrics above, dashboards exist for cost and latency by team and model, and alerting is configured on error rate spikes and latency degradations.

### First model evaluation

By the end of Phase 2, run the organization's first formal model evaluation exercise. The purpose is twofold: to produce an evidence-based recommendation for one or two real use cases (updating or confirming the approved model list), and to establish the evaluation methodology as a repeatable process.

Select two to three models that are plausible candidates for a use case where teams have expressed uncertainty. Collect real prompt-completion pairs from that use case — not synthetic benchmarks, but actual examples of the task. (Public benchmarks like MMLU are useful for a first-pass narrowing but are increasingly saturated and do not reflect your data.) Evaluate each model on the same examples using a consistent rubric: output quality (rated by domain experts, not just engineers), latency, cost per task, and any use case-specific constraints (safety, format compliance, language coverage). Document the methodology and findings. This is the first entry in what becomes the organization's model evaluation record.

**Phase 2 deliverable:** A shared embedding service is in production. Vector store infrastructure is provisioned and documented. Reference architectures for RAG, agent orchestration, and structured output exist and are linked from developer documentation. LLM observability dashboards are live. The first formal model evaluation is complete and documented.

---

## Phase 3: Developer enablement and governance integration (weeks 13–20)

Phase 3 is about making the platform the path of least resistance: easier to use than the alternatives, integrated into governance so that using the platform means being governed, and maintained in a way that teams can depend on.

### Internal AI SDK or starter kit

Publish a thin internal SDK or starter kit that wraps the API gateway with authentication, logging, retry logic, and error handling already implemented. The goal is to reduce the integration work for a new team from two to three days to two to three hours. The SDK should be opinionated: one recommended way to initialize a client, one way to handle retries, one way to emit logs. Teams that need to deviate from the defaults can, but the defaults should cover 90% of use cases correctly. <!-- noev: design rule-of-thumb, not a sourced statistic -->

Publish the SDK in the same repository management system teams already use. Version it. Write a changelog. Treat it as a first-class software product, because it is — its customers are the internal engineering teams building on the platform.

### Model evaluation playbook

Formalize the process any team can use to request that a new model be added to the approved list. The playbook should specify: what evidence is required (evaluation results on a defined set of tasks, cost analysis, review of vendor data handling terms), who reviews the request, how long the review takes, and what the outcome options are (approved, approved with restrictions, deferred pending more evidence, rejected). A defined process prevents both the failure mode of the approved model list becoming a gatekeeping mechanism and the failure mode of it becoming irrelevant because teams add models informally without any review.

### Governance integration

The AI platform and the AI governance function are complementary, not competing. Platform infrastructure is the mechanism through which several governance policies become enforceable rather than merely aspirational.

Integrate the model registry with the governance model inventory: every model added to the platform registry should automatically appear in the governance inventory, not require a separate manual update. Configure the API gateway to enforce approved-use policies where technically feasible — rejecting calls to models that are not on the approved list, enforcing per-team spending limits, and flagging requests that match patterns associated with prohibited use cases. Route observability data into the risk monitoring program rather than keeping it siloed in the platform team.

The governance integration also runs in the other direction: the governance function's review of new use cases should include a platform review step, so that use cases with unusual infrastructure requirements (very high request volumes, specific data residency requirements, unusual latency constraints) are identified during intake rather than after deployment.

### Platform change management process

A platform that changes without notice breaks every team that depends on it. Define a change management process before teams are deeply dependent on the platform, not after the first incident.

At minimum: a communication channel where platform changes are announced (a dedicated Slack channel or mailing list, not just a Jira ticket), a notice period for breaking changes (two weeks is a floor for most organizations; four weeks for changes affecting many teams), a definition of what constitutes a breaking change (any change to API contracts, authentication mechanisms, or model behavior that could cause existing integrations to fail), and a deprecation policy for models being removed from the approved list (how much notice, what the migration path is, who is responsible for the migration).

### Office hours and practitioner FAQ

For the first thirty days after Phase 3 capabilities are published, run weekly office hours: a one-hour open session where any engineer can bring questions, integration problems, or feedback. This is the highest-yield investment in developer enablement in the early platform lifecycle. The questions that come up repeatedly in office hours reveal the gaps in documentation and the confusing parts of the platform design. Fix those gaps between sessions.

Maintain a practitioner FAQ that captures the most common questions and their answers. The FAQ is more useful than documentation in many cases because it is indexed to the questions people actually ask rather than the information the platform team thinks they need.

**Phase 3 deliverable:** An internal AI SDK is published, versioned, and used by at least one team outside the platform team. A model evaluation playbook exists and has been used at least once. The model registry and governance model inventory are integrated. The API gateway enforces approved model and spending policy. A platform change management process is documented and communicated. A practitioner FAQ is live.

---

## Vendor evaluation

Vendor selection for AI platform components — model providers, orchestration frameworks, vector databases, observability tools — is a source of disproportionate long-term cost if handled poorly. It also has to be done against a moving target: in the eighteen months to mid-2026, major orchestration frameworks shipped breaking 1.0 releases, two MLOps tools changed owners, and OpenAI deprecated a flagship API. The core discipline: define your evaluation criteria before talking to vendors. Conversations with vendors will reshape your criteria in the direction of their strengths if you enter those conversations without anchoring criteria.

### Evaluation criteria

**Capability fit** is the minimum bar. Does the product do what your use cases require? Vendor demonstrations always show the happy path; your evaluation should include the failure cases, the edge cases, and the use cases where you expect the product to underperform.

**Total cost of ownership** includes license or usage cost, but also the cost to build and maintain the integration, the operational overhead of running the system, and the cost of switching if the product proves inadequate. Products with low per-unit pricing but high integration complexity frequently have higher total cost than products with higher per-unit pricing but clean integration patterns.

**Integration complexity** is especially important for AI platform components, where data flows across multiple systems. A vector database that requires a custom ingestion pipeline for every data source is not actually plug-and-play. Evaluate integration complexity against your specific data infrastructure, not against the vendor's reference architecture.

**Vendor stability and contract terms** matter more for infrastructure than for application-level tools. A model provider that changes pricing, deprecates models without adequate notice, or updates model behavior without version locking creates downstream operational risk. Evaluate contract terms for: notice periods for model changes, data processing agreements that cover your data obligations, audit rights, and SLA definitions that address output quality, not just uptime.

**Compliance posture** is non-negotiable for regulated industries. Data residency, certifications (SOC 2, ISO 27001), HIPAA eligibility (a signed Business Associate Agreement is legally required before protected health information can flow to a vendor), and the specifics of how training and fine-tuning use customer data are all evaluation criteria, not afterthoughts. SOC 2 and ISO 27001 are the de facto security-attestation baseline for enterprise AI procurement; treat their absence as a finding, not a footnote.

### Structured POCs

For shortlisted vendors, run a structured proof of concept. Give two or three vendors the same representative use case with the same sample data. Define the scoring rubric before the POC starts and apply it consistently. POC tasks should include: the representative happy path, edge cases specific to your use case, a failure case (what happens when the input is malformed or the model produces a low-confidence output), and an operational task (how hard is it to debug a problem, retrieve logs, or identify what went wrong in production).

Score results using the evaluation criteria above. Document the scores and the reasoning. Vendor selection decisions backed by POC evidence are significantly easier to defend to stakeholders than decisions based on reputation, sales demos, or engineering preference.

### The managed cloud provider trap

AWS, GCP, and Azure all offer managed AI/ML platform services — SageMaker, Vertex AI, Azure ML — that provide genuine convenience. Infrastructure management overhead is lower, integrations with other cloud services are tighter, and the procurement relationship is consolidated. These are real advantages.

The risk is lock-in that accumulates invisibly. Managed services in each cloud provider are designed to integrate smoothly with each other and awkwardly with competitors. A production ML pipeline built on SageMaker Pipelines, using SageMaker Feature Store, deployed via SageMaker endpoints, and monitored via CloudWatch is not straightforwardly migrated to Azure or GCP. The marginal cost of that migration may be acceptable; the important question is whether you have estimated it before committing.

Evaluate managed cloud services against the following: what is the marginal cost of running this workload cloud-agnostically using open-source or multi-cloud alternatives? If that marginal cost is low, the lock-in risk is low. If that marginal cost is high, you are making a strategic bet on a cloud provider relationship — make that bet consciously, not by default.

---

## Integration architecture patterns

Three patterns cover the majority of enterprise AI integration scenarios. Most use cases map to one of these patterns; understanding which pattern applies clarifies the integration requirements before detailed design begins.

### Pattern 1: API-first integration

The simplest and most maintainable pattern. Existing systems call the AI platform's internal API. The platform handles model selection, prompt management, and response parsing. The consuming system treats the AI platform as an opaque service: request goes in, enriched or generated output comes back.

This pattern works best for greenfield integrations, new workflows built alongside the AI capability, and use cases where the consuming system can tolerate the latency of an API call. The interface is clean, the coupling is loose, and the AI platform can be updated without touching the consuming system as long as the API contract is stable. Operational complexity is low: the integration is a standard service-to-service call with standard observability.

The main limitation is latency. If the consuming system has sub-100ms response time requirements and the AI model call takes 500ms, the API-first pattern is not viable without a caching layer or an asynchronous variant.

### Pattern 2: Event-driven integration

Existing systems publish events; the AI platform subscribes to those events and produces enriched outputs that are published back for downstream consumption. A customer support ticket arrives, the AI platform subscribes to a ticket-created event, generates a summary and classification, and publishes an enriched ticket event, and the support system consumes the enriched event and updates the ticket record.

This pattern is best for retrofitting AI capabilities into existing event-driven architectures, for use cases where AI enrichment does not need to be synchronous with the triggering action, and for high-volume use cases where decoupling load from the consuming system's request/response cycle matters. The AI platform can scale independently of the consuming system, and backpressure handling is explicit via the event queue rather than implicit via timeout behavior.

The tradeoff is complexity. Event-driven integrations require reliable event infrastructure, careful design of event schemas, and explicit handling of reprocessing (what happens when the AI call fails — is the event retried, dropped, or routed to a dead-letter queue?). The observability requirements are higher: tracing a request through an event-driven integration requires correlation IDs that span systems.

### Pattern 3: Embedded integration

The AI model is called synchronously within an existing transaction, as part of the transaction's execution path. A loan application is submitted, the application service calls the AI platform's risk assessment endpoint inline, the AI risk score is incorporated into the application's approval decision, and the transaction completes.

This pattern is appropriate for high-frequency, time-sensitive use cases where the AI output must be available before the transaction can complete. It requires: low-latency models (response time budgets are often under 200ms for embedded use cases), careful fallback design (what happens when the AI call fails or times out — does the transaction fail, or does it proceed with a default?), and explicit circuit-breaker logic to prevent AI latency spikes from cascading into application availability degradation.

Embedded integration also has the tightest coupling of the three patterns. Changes to the AI call interface or the AI output schema require coordinated changes in the consuming application. Test coverage for the embedded integration must include failure cases — AI service unavailable, AI response malformed, AI response outside expected bounds — because those failure cases affect live transaction processing.

---

## What good looks like at 90 days

A well-built platform function at the 90-day mark looks like this:

The **API gateway is live** and all active AI integrations are routed through it. The gateway has been in production long enough that the initial migration friction is resolved and teams experience it as the normal path, not as an overhead.

**Cost attribution is operational.** There is a dashboard that any team lead or engineering manager can consult to see their AI spend in near-real-time. Alerts have fired at least once and were acted on. The monthly AI cost conversation happens against actual data rather than estimates.

**An approved model list is published and maintained.** Teams know where to look to answer "which model should we use?" and the answer reflects at least one actual model evaluation, not just vendor recommendations. The list has been updated at least once.

**Shared embedding infrastructure is in use by at least two teams** other than the platform team. This is the litmus test for whether the shared infrastructure is actually shared or whether it exists in theory but teams are still building their own.

**Developer documentation is used.** The signal here is qualitative: engineers who join projects or onboard to the platform stop asking "how do I authenticate?" and "which model should I use for this?" because the documentation answers those questions clearly enough that the questions don't need to be asked.

**At least one formal model evaluation is complete** with documented methodology, results, and a recommendation that was acted on.

**The platform change process is defined and has been exercised.** A change has been communicated through the defined channel with the defined notice period. Teams received the communication and were not surprised by the change.

**Governance integration is functional.** The model registry feeds the governance model inventory. The API gateway enforces the approved model policy. At least one governance review has used platform observability data.

This is not a complete platform. Significant maturity work lies ahead — advanced evaluation infrastructure, fine-tuning workflows, multi-region deployment, self-service tooling for teams to manage their own use cases within defined guardrails. But a platform that hits the 90-day targets above is functional, used, and providing value. That is the foundation everything else is built on.

---

For framework context on the technology architecture decisions underlying the platform, see the [Technology Architecture Framework](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md). For a survey of tool options at each layer of the stack, see [The AI Tooling Landscape](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/03-tooling-landscape.md). To score your platform against a maturity model, work through the [Platform Maturity Scoring assessment](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/05-assessment-platform-maturity-scoring.md).

---

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **McKinsey — *The State of AI*, 2025.** 88% of respondents report regular AI use in at least one business function, compared with 78% a year ago. [View source](https://www.mckinsey.com/capabilities/quantumblack/our-insights/the-state-of-ai){#ev-mckinsey-state-of-ai-2025-adoption} · verified 2026-06-20 · primary
- **S&P Global Market Intelligence — *Generative AI shows rapid growth but yields mixed results (Voice of the Enterprise: AI & Machine Learning, Use Cases)*, 2025.** The proportion of companies that abandon most of their AI initiatives has increased from 17% to 42%, with the average organization scrapping 46% of its proof-of-concept projects prior to production. [View source](https://www.spglobal.com/market-intelligence/en/news-insights/research/2025/10/generative-ai-shows-rapid-growth-but-yields-mixed-results){#ev-sp-global-vote-2025-abandoned-ai-initiatives} · verified 2026-06-21 · ⚠ secondary mirror
- **Microsoft & LinkedIn — *2024 Work Trend Index Annual Report*, 2024.** 78% of AI users are bringing their own AI tools to work (BYOAI). [View source](https://www.microsoft.com/en-us/worklab/work-trend-index/ai-at-work-is-here-now-comes-the-hard-part){#ev-microsoft-work-trend-2024-byoai} · verified 2026-06-20 · primary
- **IBM — *Cost of a Data Breach Report*, 2025.** having a high level of shadow AI ... added an extra USD 670,000 to the global average breach cost ... Shadow AI ... was a factor in 20% of breaches (2025 global average breach cost fell 9% to USD 4.44 million). [View source](https://www.ibm.com/reports/data-breach){#ev-ibm-cost-of-breach-2025-shadow-ai} · verified 2026-06-21 · primary
- **FinOps Foundation — *The State of FinOps*, 2025.** AI spending is now managed by the majority of respondents (63% up from 31% last year). [View source](https://data.finops.org/2025-report/){#ev-finops-foundation-state-of-finops-2025-tracking-spend} · verified 2026-06-20 · primary
- **Menlo Ventures — *State of Generative AI in the Enterprise*, 2025.** We estimate Anthropic now earns 40% of enterprise LLM spend ... OpenAI lost nearly half of its enterprise share, falling to 27% from 50% in 2023. [View source](https://menlovc.com/perspective/2025-the-state-of-generative-ai-in-the-enterprise/){#ev-menlo-ventures-state-genai-2025-llm-spend-share} · verified 2026-06-21 · primary
