---
type: Reference
title: "Tooling Landscape"
description: "AI platform and orchestration tools, API management and cost governance, model evaluation, and developer tooling for the enterprise AI platform layer."
tags: [ai-platform, tooling, orchestration, mlops, api-governance]
timestamp: "2026-06-18"
---

## How to Use This Landscape

This is a survey of the platforms and tools that sit in the AI platform layer — the infrastructure between your organization's data pipelines and the end-user applications that consume AI capabilities. That layer covers LLM orchestration, agent runtimes, API management, model evaluation, vector retrieval, MLOps, and developer enablement tooling. It is distinct from the governance and monitoring tools covered in the [AI Governance & Risk tooling landscape](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/03-tooling-landscape.md), and from the data pipeline tooling that belongs to [Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md). What this page covers is the orchestration, routing, evaluation, and developer infrastructure that the [technology architecture framework](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md) calls the platform layer.

One honest caveat up front: this is the fastest-moving segment of the AI tooling market, and the past eighteen months prove it. Between late 2024 and mid-2026, LangChain and LangGraph shipped their first 1.0 releases, Microsoft folded AutoGen and Semantic Kernel into a single successor framework, OpenAI deprecated its Assistants API, and three of the tools below changed corporate owners. Licensing has shifted too — some tools opened up, others moved enterprise features behind a commercial tier. Use this landscape as a starting map, not a procurement checklist. Verify each tool's current license and roadmap against its own documentation, and run proof-of-concept work before committing at scale.

---

## LLM Orchestration Frameworks

Orchestration frameworks provide the abstractions — chains, pipelines, prompt templates, memory, retrieval connectors — that developers use to build LLM-powered applications. The honest framing: most of what these frameworks do can also be done with direct API calls and a modest amount of application code. The question is whether the abstraction saves enough time to justify the added dependency and complexity.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[LangChain](https://www.langchain.com)** | The most widely adopted LLM orchestration library (MIT-licensed). Reached its **1.0 GA in October 2025**, which collapsed the framework around a single high-level agent abstraction built on LangGraph internals plus a middleware system — a deliberate simplification after years of accumulated complexity. Large ecosystem of model, vector store, and tool integrations. | Teams that need rapid prototyping with many integration points, or where the broader LangChain/LangSmith ecosystem is already in use. For simple retrieval-augmented generation or single-step LLM calls, direct API calls are often cleaner. |
| **[LangGraph](https://www.langchain.com/langgraph)** | A low-level, graph-based orchestration runtime for stateful, durable agents — checkpointing, resumable execution, human-in-the-loop, explicit state management. Also reached **1.0 GA in October 2025** and now serves as the engine beneath LangChain v1. MIT-licensed. | Multi-step workflows where control flow matters — branching logic, human-in-the-loop checkpoints, retries on failure, and long-running agent loops. The better choice than the high-level agent abstraction when you need deterministic, auditable, durable execution paths. |
| **[LlamaIndex](https://www.llamaindex.ai)** | MIT-licensed data/agent framework, historically focused on RAG and now **repositioned around agentic document processing and Workflows** (its LlamaParse/LlamaCloud document-extraction products are central). Strong at document parsing, chunking strategies, and structured-data connectors. Still on a 0.x version line. | Applications where document ingestion and retrieval quality are the primary concern: knowledge bases, document Q&A, enterprise search, and document-extraction pipelines. A strong default for teams building retrieval- and document-heavy systems rather than general-purpose agents. |
| **[Semantic Kernel](https://learn.microsoft.com/en-us/semantic-kernel/)** (Microsoft) | Microsoft's model-agnostic SDK (C#, Python, Java) for LLM integration — plugins, function calling, memory connectors. **Now folded into the Microsoft Agent Framework and effectively in maintenance mode** (bug and security fixes); new work is directed to the successor framework. | Existing .NET/Azure deployments already built on Semantic Kernel. New projects in the Microsoft ecosystem should evaluate the Microsoft Agent Framework instead (see Agent Runtimes below). |
| **[Haystack](https://haystack.deepset.ai)** (deepset) | Apache-2.0 Python framework for production RAG and agent pipelines, with a modular pipeline abstraction and strong retrieval components. The current 2.x line (`haystack-ai`) is a substantial rewrite; the legacy 1.x line reached end-of-life in March 2025. | Enterprise search, document intelligence, and information extraction where the retrieval pipeline is complex and needs to be independently testable and maintainable, with a permissive license and no single-vendor cloud dependency. |

---

## Agent Runtimes and Multi-Agent Frameworks

Agent runtimes go beyond single-turn orchestration — they manage agent loops, tool use, state across turns, and in multi-agent settings, coordination between multiple LLM-powered actors. The distinction that matters in practice: some frameworks give you primitives to build agents your way; others are opinionated runtimes that enforce specific patterns. This category saw the most consolidation of any in the past year — read the change notes carefully.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[LangGraph](https://www.langchain.com/langgraph)** | See Orchestration above. Its graph-based, durable execution model is specifically well-suited to agent loops with conditional transitions, tool-use cycles, and human approval steps. MIT-licensed; 1.0 GA October 2025. | Building agents that need explicit control over execution state, conditional branching, durability across restarts, and auditability of the agent's decision path. |
| **[Microsoft Agent Framework](https://learn.microsoft.com/en-us/agent-framework/)** | Microsoft's **unified successor to AutoGen and Semantic Kernel** (Python and .NET, open-source SDK). Public preview October 2025, 1.0 GA in spring 2026. Combines AutoGen's multi-agent runtime with Semantic Kernel's enterprise integration. | Enterprises on the Microsoft/Azure stack that want a first-party, supported agent framework. The recommended starting point for new Microsoft-ecosystem agent work, in place of the now-maintenance-mode AutoGen and Semantic Kernel. |
| **[AutoGen](https://microsoft.github.io/autogen/)** (Microsoft) | Multi-agent framework built on an async actor-model runtime (code MIT-licensed). Agents communicate as conversational entities; supports human-in-the-loop participation. **Now merged into the Microsoft Agent Framework and in maintenance mode** — community-managed, no major new development. | Existing AutoGen deployments. New multi-agent projects should evaluate the Microsoft Agent Framework, which is the supported continuation of this line. |
| **[CrewAI](https://www.crewai.com)** | An opinionated multi-agent framework (MIT-licensed) that models agent teams as "crews" with defined roles, goals, and task assignments. Independent of LangChain. Reached **v1.0 in October 2025**; the commercial offering is branded CrewAI AMP. | Teams that want a pre-structured way to run multi-agent pipelines with defined roles and sequential or parallel task execution; good for process-automation workflows. Less appropriate when the orchestration logic needs heavy custom control. |
| **[Claude tool use & Agent SDK](https://docs.claude.com/en/docs/agent-sdk)** (Anthropic) | Anthropic's native tool-use API (client tools plus Anthropic-run server tools such as web search and code execution) and the **Claude Agent SDK** (renamed from the Claude Code SDK in September 2025) for building production agents with MCP, subagents, hooks, and Skills. The Python SDK is MIT-licensed; the TypeScript SDK is proprietary. | Use cases where Claude is the primary model. Direct tool use keeps orchestration logic in the application layer for maximum control and debuggability; the Agent SDK is the higher-level path for production agents. |
| **[OpenAI Agents SDK](https://openai.github.io/openai-agents-python/)** | OpenAI's lightweight, provider-agnostic multi-agent framework (MIT-licensed) — handoffs, guardrails, and built-in tracing. The production-grade successor to the experimental Swarm project, which is now retired. Python and TypeScript. | Teams building multi-agent systems who want a minimal, unopinionated framework with first-party tracing. A reasonable default for OpenAI-centric stacks, though it works across providers. |
| **[OpenAI Assistants API](https://platform.openai.com/docs/assistants/overview)** | OpenAI's hosted, stateful assistant runtime (Threads, Runs, Code Interpreter, File Search). **Deprecated: announced August 2025 with a hard sunset of August 26, 2026.** OpenAI directs new development to the Responses API. | Nothing new — do not start here. Existing Assistants API integrations should plan migration to the Responses API ahead of the 2026 sunset. Included here specifically because reference material still points to it. |

---

## API Gateway and Cost Management

As organizations move from individual LLM experiments to production deployments at scale, API management becomes a significant operational concern. The problems are consistent: routing requests to the right model, tracking costs by team or use case, rate limiting to prevent runaway spend, caching repeated queries, and maintaining an audit log for compliance. Many large enterprises build internal proxy layers on top of these tools to enforce additional governance controls.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[LiteLLM](https://www.litellm.ai)** | Open-source proxy/gateway that provides a unified OpenAI-format API across 100+ LLM providers. Handles request routing, cost tracking, rate limiting, fallbacks, and load balancing. The core is MIT-licensed; an `enterprise/` directory holds proprietary add-ons. Widely used as the foundation for internal AI API gateways. | The default starting point for teams that need to abstract provider APIs, enforce spend controls, and maintain a single interface across models. The open-source option most commonly used in enterprise AI platform builds. |
| **[Portkey](https://portkey.ai)** | AI gateway and observability platform combining routing across a large provider set, caching, cost analytics, guardrails, and prompt management. Open-core: the gateway is MIT-licensed, with a managed cloud and enterprise tier. | Teams that want a managed gateway with more out-of-the-box observability, guardrails, and prompt management than LiteLLM provides, without building the analytics layer themselves. |
| **[Helicone](https://www.helicone.ai)** | Observability-first proxy that logs requests, tracks spend by user or session, rate limits, and caches — typically a one-line base-URL change to integrate. Open source (the core platform is Apache-2.0), with a newer Rust-based AI Gateway component; confirm the license on the specific component you deploy. | Teams that primarily need cost visibility, session-level logging, and simple caching, especially where rapid time-to-integration matters more than advanced routing. |
| **[Braintrust](https://www.braintrust.dev)** | Primarily an evaluation and observability platform (see below) that also ships an AI gateway/proxy for logging and tracing LLM calls. The proxy is MIT-licensed; the platform is proprietary SaaS. | Teams already using Braintrust for evaluation that want to consolidate observability and gateway functions into one platform. |
| **Cloud-provider AI gateways** | Azure API Management now ships explicit **GenAI/AI gateway capabilities** (token limits and quotas, semantic caching, load balancing, content safety). AWS provides Amazon Bedrock as a unified managed model API plus published reference architectures for a gateway pattern (there is no AWS product literally named "AI gateway"). Both proprietary. | Enterprises standardized on a single cloud that want gateway capabilities integrated with existing API management, IAM, and billing rather than running a separate open-source proxy. |
| **Internal AI API proxies** | Many enterprises at scale build internal proxy layers — often on top of LiteLLM or a cloud API management service — to enforce SSO-based authentication, team-level budgets, data-residency routing, and audit logging integrated into enterprise SIEM systems. | Organizations with strict data governance, compliance logging requirements, or multi-cloud routing needs that off-the-shelf gateways don't fully address. The pattern most common in large financial services and healthcare AI deployments. |

---

## Model Evaluation and Selection

Evaluation is one of the most underinvested parts of the AI platform layer in early enterprise deployments — and one of the areas that causes the most problems at scale. The tools here address two different needs: platforms for running ongoing evaluations against your own data and tasks, and public benchmarks that provide reference points for comparing models before deployment.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[Braintrust](https://www.braintrust.dev)** | Evaluation platform providing dataset management, eval scoring (LLM-as-judge and custom metrics), experiment tracking, and comparison across model versions or prompts, plus a proxy for logging production calls. Proprietary SaaS; its `autoevals` library is MIT-licensed. | Teams that need a structured eval platform with strong experiment tracking — among the most established dedicated LLM evaluation platforms. |
| **[LangSmith](https://www.langchain.com/langsmith)** | LangChain's tracing, evaluation, and deployment platform (proprietary). Traces LLM calls and chains, supports dataset-based evals, and provides a UI for reviewing and annotating outputs. Tightly integrated with the LangChain/LangGraph ecosystem; the managed deployment product was renamed LangSmith Deployment. | Teams already using LangChain/LangGraph who want evaluation, observability, and deployment in the same ecosystem. |
| **[PromptLayer](https://promptlayer.com)** | Prompt management, versioning, A/B testing, and evaluation platform (proprietary; SDK Apache-2.0). Tracks prompt performance over time and provides a visual interface for managing prompt templates. | Teams focused on systematic prompt iteration and version control, particularly where prompt engineers and developers collaborate and need shared visibility into what changed and what the effect was. |
| **[Weights & Biases Weave](https://wandb.ai/site/weave/)** | W&B's GenAI tracing and evaluation framework (Weave SDK Apache-2.0; platform commercial). Logs LLM calls and supports evaluation experiments within the broader W&B platform. **W&B was acquired by CoreWeave in 2025.** | Organizations already using W&B for ML experiment tracking that want to bring LLM evaluation into the same infrastructure. |
| **[RAGAS](https://github.com/vibrantlabsai/ragas)** | Open-source (Apache-2.0) framework for evaluating RAG pipelines — faithfulness, answer relevancy, context precision, and context recall, scored via LLM-as-judge, plus synthetic test-data generation. The repository moved to the `vibrantlabsai` organization (commercial steward Vibrant Labs). | Any team building RAG applications — RAGAS provides the evaluation vocabulary and metrics that are otherwise hard to define for retrieval-augmented generation specifically. |
| **[OpenAI Evals](https://github.com/openai/evals)** | OpenAI's open-source (MIT) framework for evaluating models on custom tasks, with a standardized task format. Note the split: the **open-source repo remains active, but OpenAI's hosted Evals product is being deprecated** (read-only and shutdown dates announced for late 2026). | Teams that want a structured, community-backed evaluation framework with a standard task format, more suitable for systematic model comparison than for ongoing production monitoring. |
| **Public benchmarks** | **[LMArena](https://lmarena.ai)** (formerly LMSYS Chatbot Arena, rebranded in 2024 and now operated by an independent company) provides crowdsourced human-preference rankings via pairwise voting — useful for general capability reference. **MMLU** tests knowledge breadth but is now largely saturated near the top, with **MMLU-Pro** the harder successor. **MT-Bench** (multi-turn instruction following) is now mostly historical. Domain-specific benchmarks (MedQA, FinanceBench) give more relevant reference points for sector deployments. | Establishing a capability baseline before selecting a model for a new use case; not a substitute for evaluation on your own data and tasks, but a useful starting point for narrowing the candidate set. Prefer current, unsaturated benchmarks. |

---

## Vector Databases and Retrieval Infrastructure

Vector databases store and index high-dimensional embeddings and serve nearest-neighbor queries that power retrieval-augmented generation. This remains a competitive but largely independent market — despite periodic acquisition rumors, none of the major vector databases below changed ownership in 2024–2026; the trend has been continued independent fundraising and feature convergence (hybrid search, reranking, managed embeddings). The default starting point for many teams is now an extension on their existing relational database before moving to a dedicated vector store.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[pgvector](https://github.com/pgvector/pgvector)** | PostgreSQL extension (PostgreSQL/BSD-style license) that adds vector storage and similarity search (cosine, L2, inner product) to existing Postgres, with HNSW and IVFFlat indexing. Community-maintained; recent releases added half-precision and sparse vectors and iterative index scans. No new infrastructure if you already run Postgres. | The recommended starting point for most teams. Up to roughly tens of millions of vectors without extreme latency requirements, pgvector on an existing Postgres instance handles the workload. Move to a dedicated vector database only when you hit real scaling constraints. |
| **[Pinecone](https://www.pinecone.io)** | Managed, serverless vector database designed for production-scale similarity search (proprietary, cloud-only). Handles indexing, scaling, and infrastructure management as a service. The company saw a CEO transition in 2025 but remains independent. | Teams that need a managed vector database at scale and want to minimize operational overhead; the easiest path to production-scale vector search without running infrastructure, at the cost of vendor lock-in. |
| **[Weaviate](https://weaviate.io)** | Open-source (BSD-3-Clause) vector database with built-in hybrid search (vector + keyword), multi-tenancy, and modules for automatic vectorization. Self-hosted or managed cloud. | Organizations that need hybrid retrieval, want to self-host for data-residency reasons, or need multi-tenancy to serve multiple internal business units from one cluster. |
| **[Qdrant](https://qdrant.tech)** | Open-source (Apache-2.0) vector search engine written in Rust, focused on performance and rich payload filtering, with GPU-accelerated indexing in recent releases. Self-hosted and cloud-managed. | Use cases where retrieval must combine vector similarity with structured metadata filters — for example, semantically similar documents that also match a date range, department, or access tier. |
| **[Chroma](https://www.trychroma.com)** | Open-source (Apache-2.0), AI-native search infrastructure (vector, full-text, metadata) with a simple Python-native API; a managed Chroma Cloud is now generally available and the core was rewritten in Rust. | Rapid local prototyping and development where ease of setup matters, with a managed path to production via Chroma Cloud as the retrieval layer hardens. |
| **[Milvus](https://milvus.io)** (Zilliz) | Open-source (Apache-2.0), cloud-native vector database built for billion-scale workloads, with managed Zilliz Cloud. A graduated LF AI & Data project. | High-scale deployments that need a purpose-built, horizontally scalable vector database and are comfortable operating distributed infrastructure (or using the managed Zilliz Cloud). |

---

## Memory and Context Frameworks

This is the newest category in this landscape, and the one where the vendor marketing outpaces the settled technology by the widest margin (see [MCP and the Context Gap](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/06-mcp-and-the-context-gap.md) for why). Stripped of "context layer" branding, these tools solve one specific, narrower problem: giving an agent durable memory across sessions, on top of — not instead of — the [Model Context Protocol](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/06-mcp-and-the-context-gap.md) and the vector databases above. Every product below launched or materially repositioned within the past eighteen months; treat this table as a starting map, not a settled category, and verify current licensing and deployment options directly.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[Mem0](https://mem0.ai)** | Memory layer that extracts, updates, and retrieves facts from agent interactions automatically (an "add / learn / retrieve" model), condensing chat history into compact memories to cut tokens and latency. Core is Apache-2.0 licensed; offers both a managed cloud (with SOC 2 Type 1 and HIPAA-oriented compliance features) and self-hosted deployment (Kubernetes, private cloud, or air-gapped) behind the same API. | Teams that want a managed or self-hosted drop-in memory API without building extraction/retrieval logic themselves, and that value having both a cloud and an air-gapped deployment path on the same interface. |
| **[Cognee](https://www.cognee.ai)** (topoteretes) | Open-source (Apache-2.0) agent memory platform that turns ingested data into a graph-based memory — entities and relationships, not just embeddings — so agents can recall structured context across sessions. Self-hosted by default, with an optional managed Cognee Cloud tier; exposes both direct SDKs and an MCP server interface, and integrates with multiple agent frameworks (Claude Code, LangGraph, and others). | Teams that want the memory store itself to be a real, queryable knowledge graph rather than a flat key-value or vector cache, and that prefer to start fully self-hosted before considering a managed tier. |
| **[Zep](https://www.getzep.com)** | Proprietary managed memory platform built around a "Context Graph Engine" that builds a graph from chat history and business data, tracks when facts change over time (invalidating outdated facts while preserving history), and targets sub-200ms retrieval. Deployment options are Zep Cloud, Cloud with customer-held encryption keys, or bring-your-own-cloud (BYOC) — no self-hosted open-source tier for the managed platform itself. | Teams that need temporal reasoning — not just "what do we know," but "what did we know, and when did it change" — and are comfortable with a managed or BYOC deployment rather than fully self-hosting. |
| **[Graphiti](https://github.com/getzep/graphiti)** (Zep) | The open-source (Apache-2.0) temporal knowledge-graph engine that powers Zep's managed platform, but is independently self-hostable. Tracks validity windows per fact, traces every derived fact back to its source data, and combines semantic search, keyword matching, and graph traversal for retrieval. | Teams that want Zep's temporal-graph approach without the managed service — building agent memory on infrastructure they fully control and can inspect. |
| **[Redis Iris](https://redis.io/iris)** (Context Retriever + Agent Memory) | Redis's context-and-memory platform, announced May 2026: **Context Retriever** lets teams define a semantic model of business entities and relationships, then auto-generates MCP tools agents use instead of querying databases directly, with access rules enforced server-side; **Agent Memory** manages short-term conversational state and longer-term durable memory in the same Redis infrastructure. Both components are in preview as of launch. Proprietary; built on Redis. | Organizations already running Redis for agent-runtime state that want memory and a governed, agent-facing retrieval layer added to infrastructure they already operate, rather than adding a separate vendor. |

---

## MLOps and Model Registry

Full MLOps tooling — experiment tracking, model registries, data versioning, and model serving — is most relevant for organizations that are fine-tuning or training models, not just consuming APIs. For teams using foundation models via API, the relevant subset is narrower: a model registry to track which version of what model is deployed where, and a serving layer if fine-tuned models are deployed. Notably, several of these tools have pivoted toward GenAI/agent workflows, and the ownership of two changed in 2025.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[MLflow](https://mlflow.org)** | Open-source (Apache-2.0) platform for experiment tracking, model registry, and deployment, stewarded by Databricks. **MLflow 3.0 (2025) re-centered the project on GenAI** — tracing, agent evaluation, and a prompt registry — alongside the classic ML lifecycle features. | Organizations doing model training or fine-tuning that need a governed model registry with full lineage, increasingly also those that want GenAI tracing and evaluation in the same tool. The most commonly deployed open-source MLOps tool. |
| **[Weights & Biases](https://wandb.ai)** | Experiment tracking, model registry, and artifact versioning (SDK MIT; platform commercial). Polished UI and strong team-collaboration features. **Acquired by CoreWeave in 2025.** | Teams where experiment tracking and model comparison across researchers or engineers is the primary workflow, and where tracking-UI quality matters. |
| **[DVC](https://dvc.org)** (Data Version Control) | Open-source (Apache-2.0) tool for versioning data and ML pipelines using Git-compatible storage. **Acquired by lakeFS in late 2025**; the original maintainer (Iterative) had pivoted toward its DataChain product. | Organizations where data versioning and pipeline reproducibility are the primary concern — large, frequently changing datasets that must be tied to specific model versions for compliance or debugging. |
| **[Hugging Face Hub](https://huggingface.co)** | The primary public platform for sharing and downloading pre-trained models, datasets, and model cards (platform proprietary; client libraries Apache-2.0). Also available as a private Enterprise Hub for hosting proprietary fine-tuned models internally. | Teams fine-tuning open-source models that need a collaborative registry for model artifacts; also the natural first stop for evaluating open-source model candidates. |
| **[BentoML](https://www.bentoml.com)** | Open-source (Apache-2.0) framework for packaging and deploying models as production-ready APIs, with batching, resource management, and containerization; recent releases lean into LLM/vLLM serving. | Teams deploying custom or fine-tuned models that need portable, containerized serving without committing to a specific cloud ML platform's serving infrastructure. |
| **[Ray Serve](https://docs.ray.io/en/latest/serve/index.html)** | Open-source (Apache-2.0) scalable model-serving library built on Ray, supporting high-throughput, low-latency deployments with batching, model composition, and multi-model pipelines; a dedicated LLM-serving module was added in 2025. | Organizations serving models at high request volumes that need fine-grained control over batching and resource allocation, particularly large deployments where latency and throughput tuning require more control than managed platforms provide. |

---

## Developer Tooling and Prompt Management

The developer enablement layer covers the tools AI engineering teams use day-to-day: AI-assisted coding environments and prompt management systems that bring version control and observability to production prompts. As organizations mature their AI platform practice, prompt management typically moves from ad hoc (prompts hardcoded in application code) to a structured discipline with versioning, testing, and deployment workflows.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[GitHub Copilot](https://github.com/features/copilot)** | GitHub's AI coding assistant across VS Code, JetBrains, and the GitHub web UI (proprietary). Now spans inline completion, an in-IDE agent mode, an autonomous cloud coding agent (GA in 2025), and a multi-model picker. Enterprise tier includes policy controls, audit logging, and content exclusion. | The default for enterprises already on GitHub Enterprise, where license management and SSO run through existing agreements. Enterprise controls make it appropriate for regulated environments. |
| **[Cursor](https://www.cursor.com)** | AI-first code editor (a VS Code fork, proprietary) with deep model integration — inline generation, codebase-aware chat, multi-file edits, and its own Composer model. Faster and more contextually aware than basic completion for complex refactors; requires migrating to a new editor. | Engineering teams willing to adopt a new editor for more capable AI assistance, particularly large-scale refactors and tasks requiring reasoning across many files at once. |
| **[Continue.dev](https://www.continue.dev)** | Open-source (Apache-2.0) AI coding assistant for VS Code and JetBrains plus a CLI, supporting any LLM backend including self-hosted models. Gives organizations full control over which model serves code completion. | Organizations that need AI coding assistance but cannot send code to external APIs due to data governance, and teams that want to run coding assistance on internal or self-hosted models. |
| **[Langfuse](https://langfuse.com)** | Open-source LLM observability, prompt management, and evaluation platform with a self-hostable deployment. A June 2025 relicense opened essentially all product features under the MIT license (only specific enterprise directories remain commercial). **Acquired by ClickHouse in early 2026; remains open source.** | Organizations that want tracing, prompt management, and eval datasets without a LangChain dependency or a cloud-only model — the open-source, self-hostable option is a differentiator for data-sensitive environments. |
| **[PromptLayer](https://promptlayer.com)** | See Model Evaluation above. Also functions as a prompt management platform — versioning prompt templates, tracking which version served which request, and a UI for prompt iteration. | Teams that want both prompt management and request logging in a single tool. |
| **Internal prompt template libraries** | Most organizations with mature AI platform practices build internal prompt template libraries — version-controlled repositories of approved prompt patterns, role descriptions, few-shot examples, and system-prompt components. These are maintained as internal engineering assets, not off-the-shelf tools. | Any team at sufficient scale to benefit from reuse and consistency across AI applications. This pattern tends to emerge organically as organizations move from per-application prompts to a shared platform layer — worth planning for intentionally rather than inheriting inconsistently. |

---

## References

- LangChain — *LangChain and LangGraph documentation* (1.0 release notes), langchain.com
- LlamaIndex — *LlamaIndex documentation*, docs.llamaindex.ai
- Microsoft — *Semantic Kernel and Microsoft Agent Framework documentation*, learn.microsoft.com
- deepset — *Haystack documentation*, haystack.deepset.ai
- Microsoft — *AutoGen documentation*, microsoft.github.io/autogen
- CrewAI — *CrewAI documentation*, docs.crewai.com
- Anthropic — *Tool use and Claude Agent SDK documentation*, docs.claude.com
- OpenAI — *Agents SDK and Assistants API deprecation notice*, platform.openai.com / openai.github.io/openai-agents-python
- LiteLLM — *LiteLLM documentation and proxy server guide*, docs.litellm.ai
- Portkey — *AI Gateway documentation*, portkey.ai/docs
- Helicone — *Helicone documentation*, docs.helicone.ai
- Braintrust — *Braintrust documentation*, braintrust.dev/docs
- Microsoft — *Azure API Management GenAI gateway capabilities*, learn.microsoft.com/azure/api-management
- AWS — *Amazon Bedrock documentation*, aws.amazon.com/bedrock
- LangSmith — *LangSmith documentation*, docs.smith.langchain.com
- PromptLayer — *PromptLayer documentation*, docs.promptlayer.com
- Weights & Biases — *W&B and Weave documentation*, docs.wandb.ai / weave-docs.wandb.ai
- RAGAS — *RAGAS documentation*, github.com/vibrantlabsai/ragas
- OpenAI — *Evals framework*, github.com/openai/evals
- LMArena — *LMArena (formerly LMSYS Chatbot Arena) leaderboard*, lmarena.ai
- Hendrycks et al. — *Measuring Massive Multitask Language Understanding* (MMLU), arXiv 2020; Wang et al. — *MMLU-Pro*, NeurIPS 2024
- Zheng et al. — *Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena*, NeurIPS 2023
- pgvector — *pgvector: Open-source vector similarity search for Postgres*, github.com/pgvector/pgvector
- Pinecone — *Pinecone documentation*, docs.pinecone.io
- Weaviate — *Weaviate documentation*, weaviate.io/developers/weaviate
- Qdrant — *Qdrant documentation*, qdrant.tech/documentation
- Chroma — *Chroma documentation*, docs.trychroma.com
- Milvus — *Milvus documentation*, milvus.io/docs
- Mem0 — *Mem0 documentation and license*, docs.mem0.ai / github.com/mem0ai/mem0
- Cognee — *Cognee documentation*, docs.cognee.ai / github.com/topoteretes/cognee
- Zep — *Zep documentation*, help.getzep.com
- Graphiti — *Graphiti documentation*, github.com/getzep/graphiti
- Redis — *Introducing Redis Iris*, redis.io/blog/context-is-all-you-need
- MLflow — *MLflow 3 documentation*, mlflow.org/docs
- DVC — *DVC documentation*, dvc.org/doc
- Hugging Face — *Hugging Face Hub documentation*, huggingface.co/docs/hub
- BentoML — *BentoML documentation*, docs.bentoml.com
- Ray — *Ray Serve documentation*, docs.ray.io/en/latest/serve
- GitHub — *GitHub Copilot documentation*, docs.github.com/copilot
- Cursor — *Cursor documentation*, docs.cursor.com
- Continue.dev — *Continue documentation*, docs.continue.dev
- Langfuse — *Langfuse documentation*, langfuse.com/docs
