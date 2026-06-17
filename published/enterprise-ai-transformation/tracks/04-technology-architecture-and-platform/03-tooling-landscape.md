---
type: Reference
title: Tooling Landscape
description: AI platform and orchestration tools, API management and cost governance, model evaluation, and developer tooling for the enterprise AI platform layer.
tags: [ai-platform, tooling, orchestration, mlops, api-governance]
timestamp: "2026-06-17"
status: published
---

## How to Use This Landscape

This is a survey of the platforms and tools that sit in the AI platform layer — the infrastructure between your organization's data pipelines and the end-user applications that consume AI capabilities. That layer covers LLM orchestration, agent runtimes, API management, model evaluation, vector retrieval, MLOps, and developer enablement tooling. It is distinct from the governance and monitoring tools covered in the [Track 02 tooling landscape](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/03-tooling-landscape.md), and from the data pipeline tooling that belongs to Track 03. What this page covers is the orchestration, routing, evaluation, and developer infrastructure that the [technology architecture framework](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md) calls the platform layer.

One honest caveat up front: this is the fastest-moving segment of the AI tooling market. Frameworks that were the default choice eighteen months ago have acquired significant complexity and viable competitors; new tools reach production-readiness quickly; and several of the companies below have changed their pricing, open-source licensing, or product scope within the past year. Use this landscape as a starting map, not a procurement checklist. Evaluate each tool against the specific capability gap you need to fill, and run proof-of-concept work before committing at scale.

---

## LLM Orchestration Frameworks

Orchestration frameworks provide the abstractions — chains, pipelines, prompt templates, memory, retrieval connectors — that developers use to build LLM-powered applications. The honest framing: most of what these frameworks do can also be done with direct API calls and a modest amount of application code. The question is whether the abstraction saves enough time to justify the added dependency and complexity.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[LangChain](https://www.langchain.com)** | The most widely adopted LLM orchestration library. Provides chains, agents, memory, and a large ecosystem of integrations with models, vector stores, and tools. Mature documentation and community. Has accumulated significant complexity over time — the abstraction layer can make simple tasks unnecessarily verbose and debugging harder. | Teams that need rapid prototyping with many integration points, or where the broader LangChain/LangSmith ecosystem is already in use. For simple retrieval-augmented generation or single-step LLM calls, direct API calls are often cleaner. |
| **[LlamaIndex](https://www.llamaindex.ai)** | Focused specifically on data ingestion, indexing, and retrieval for LLM applications — particularly RAG pipelines. Stronger than LangChain at document parsing, chunking strategies, structured data connectors, and retrieval evaluation. Less general-purpose. | Applications where retrieval quality is the primary concern: knowledge bases, document Q&A, enterprise search over internal content. The better default for teams building RAG systems rather than general-purpose agent pipelines. |
| **[LangGraph](https://www.langchain.com/langgraph)** | A graph-based extension of LangChain for building stateful, multi-step workflows and agent loops. Models execution as a directed graph of nodes and edges, with explicit state management. Enables more controllable and inspectable agentic flows than LangChain's built-in agent abstractions. | Multi-step workflows where control flow matters — branching logic, human-in-the-loop checkpoints, retries on failure, and long-running agent loops. A better choice than standard LangChain agents when you need deterministic, auditable execution paths. |
| **[Semantic Kernel](https://learn.microsoft.com/en-us/semantic-kernel/)** (Microsoft) | Microsoft's SDK for building AI applications in C#, Python, and Java. Provides plugins (wrappers around functions and APIs), planners (that generate and execute multi-step plans), and memory connectors. Tightly integrated with Azure AI services and the Microsoft ecosystem. | Enterprises running .NET infrastructure or deeply committed to the Azure AI stack; also a reasonable choice for teams that want first-party Microsoft support rather than community-maintained libraries. |
| **[Haystack](https://haystack.deepset.ai)** | Open-source framework from deepset for building NLP and LLM pipelines, with a focus on document retrieval and question-answering systems. Provides a modular pipeline abstraction, strong retrieval components, and integrations with major vector stores. Less general-purpose than LangChain; stronger on the search and document-intelligence side. | Enterprise search, document intelligence, and information extraction use cases where the retrieval pipeline is complex and needs to be independently testable and maintainable. |

---

## Agent Runtimes and Multi-Agent Frameworks

Agent runtimes go beyond single-turn orchestration — they manage agent loops, tool use, state across turns, and in multi-agent settings, coordination between multiple LLM-powered actors. The distinction that matters in practice: some frameworks give you primitives to build agents your way; others are opinionated runtimes that enforce specific patterns. Choose based on how much control and flexibility your use case requires.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[LangGraph](https://www.langchain.com/langgraph)** | See Orchestration section above. Listed again here because its graph-based execution model is specifically well-suited to agent loops with conditional transitions, tool-use cycles, and human approval steps. The state machine abstraction maps naturally to agent behavior. | Building agents that need explicit control over execution state, conditional branching, and multi-turn task completion — particularly where auditability of the agent's decision path matters. |
| **[AutoGen](https://microsoft.github.io/autogen/)** (Microsoft) | A multi-agent framework that models agents as conversational entities that communicate with each other. Supports human-in-the-loop participation and flexible agent role assignment. Useful for workflows where two or more agents divide up a task and coordinate via messages. | Research, code generation, and complex task completion workflows where decomposing work across specialized agents is the right architecture. Requires careful prompt engineering to keep agent conversations on track. |
| **[CrewAI](https://www.crewai.com)** | An opinionated multi-agent framework built on top of LangChain that models agent teams as "crews" with defined roles, goals, and task assignments. Higher-level abstraction than AutoGen — less flexible, but faster to stand up for common patterns. | Teams that want a pre-structured way to run multi-agent pipelines with defined roles and sequential or parallel task execution; good for process automation workflows. Less appropriate when the orchestration logic needs significant custom control. |
| **[Claude with tool use](https://docs.anthropic.com/en/docs/build-with-claude/tool-use)** (Anthropic) | Anthropic's native tool use API for Claude models, enabling Claude to call functions, retrieve data, and execute multi-step tasks. Unlike framework-based agents, this keeps orchestration logic in the application layer — the developer controls the agent loop explicitly. | Use cases where Claude is the primary model and you want minimal framework overhead. Direct tool use with explicit application-layer control is often more reliable and debuggable than framework-managed agent loops for production workloads. |
| **[OpenAI Assistants API](https://platform.openai.com/docs/assistants/overview)** | OpenAI's managed agent runtime that handles thread management, tool calling, file retrieval, and code execution within a hosted environment. Abstracts away the agent loop entirely — OpenAI manages state and execution. | Teams building GPT-4-based assistants that want to offload agent infrastructure management; the trade-off is reduced control and visibility into execution. Less appropriate when you need custom tool-use logic or multi-model flexibility. |

---

## API Gateway and Cost Management

As organizations move from individual LLM experiments to production deployments at scale, API management becomes a significant operational concern. The problems are consistent: routing requests to the right model, tracking costs by team or use case, rate limiting to prevent runaway spend, caching repeated queries, and maintaining an audit log for compliance. This category addresses that layer. Many large enterprises also build internal proxy layers on top of these tools to enforce additional governance controls.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[LiteLLM](https://www.litellm.ai)** | Open-source proxy server that provides a unified API interface across 100+ LLM providers (OpenAI, Anthropic, Azure, Cohere, Hugging Face, and others). Handles request routing, cost tracking, rate limiting, fallbacks, and load balancing. Widely used as the foundation for internal AI API gateways. | The default starting point for teams that need to abstract provider APIs, enforce spend controls, and maintain a single interface across models. The open-source option most commonly used in enterprise AI platform builds. |
| **[PortKey](https://portkey.ai)** | AI gateway and observability platform combining request routing, caching, cost analytics, and guardrails. Cloud and self-hosted options. Includes a prompt management layer and an evaluation suite alongside the gateway functionality. | Teams that want a managed gateway with more out-of-the-box observability and prompt management than LiteLLM provides, without building the analytics layer themselves. |
| **[Helicone](https://www.helicone.ai)** | Observability and cost management proxy that sits in front of LLM API calls to log requests, track spend by user or session, rate limit, and cache responses. Lightweight to integrate — typically a one-line change to the API base URL. Focused more on observability than routing logic. | Teams that primarily need cost visibility, session-level logging, and simple caching — especially where rapid time-to-integration matters more than advanced routing features. |
| **[Braintrust](https://www.braintrust.dev)** | Primarily an evaluation platform (see below), but also provides a proxy layer for logging and tracing LLM calls, making it useful as a lightweight observability gateway in addition to its eval capabilities. | Teams already using Braintrust for evaluation that want to consolidate observability into the same platform rather than running a separate gateway. |
| **Internal AI API proxies** | Many enterprises running at scale build internal proxy layers — often on top of LiteLLM or a cloud provider's API management service (Azure API Management, AWS API Gateway) — to enforce organizational controls: SSO-based authentication, team-level budgets, data residency routing, and audit logging integrated into enterprise SIEM systems. | Organizations with strict data governance, compliance logging requirements, or multi-cloud routing needs that open-source gateway tools don't fully address out of the box. This is the pattern most commonly seen in large financial services and healthcare AI deployments. |

---

## Model Evaluation and Selection

Evaluation is one of the most underinvested parts of the AI platform layer in early enterprise deployments — and one of the areas that causes the most problems at scale. The tools in this section address two different needs: platforms for running ongoing evaluations against your own data and tasks (where the metrics are specific to your use case), and public benchmarks that provide reference points for comparing models before deployment.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[Braintrust](https://www.braintrust.dev)** | Evaluation platform for LLMs providing dataset management, eval scoring (via LLM-as-judge and custom metrics), experiment tracking, and comparison across model versions or prompts. Includes a proxy layer for logging production calls. | Teams that need a structured eval platform with good experiment tracking — the closest thing to Weights & Biases but designed specifically for LLM evaluation workflows. |
| **[LangSmith](https://www.langchain.com/langsmith)** | LangChain's evaluation, observability, and prompt management platform. Traces LLM calls and chains, supports dataset-based evals, and provides a UI for reviewing and annotating model outputs. Tightly integrated with the LangChain ecosystem. | Teams already using LangChain/LangGraph who want evaluation and observability in the same ecosystem. Less useful as a standalone eval platform if the orchestration layer is built differently. |
| **[PromptLayer](https://promptlayer.com)** | Logging, versioning, and evaluation platform for prompts. Tracks prompt performance over time, supports A/B testing of prompt variants, and provides a visual interface for managing prompt templates. | Teams focused on systematic prompt iteration and version control — particularly useful where prompt engineers and developers are collaborating on prompts and need shared visibility into what changed and what the effect was. |
| **[Weights & Biases Prompts](https://wandb.ai/site/solutions/llmops)** | W&B's LLMOps extension providing prompt tracking, LLM call logging, and evaluation experiment tracking within the broader W&B platform. Most useful for teams already using W&B for ML experiment tracking who want to extend the same workflows to LLM applications. | Organizations already using W&B for ML model training that want to bring LLM evaluation into the same experiment tracking infrastructure. |
| **[RAGAS](https://ragas.io)** | Open-source framework specifically designed for evaluating RAG pipelines. Provides metrics for faithfulness (does the answer follow from the retrieved context?), answer relevancy, context precision, and context recall. Uses LLM-as-judge for scoring. | Any team building RAG-based applications — RAGAS provides the evaluation vocabulary and metrics that are otherwise hard to define and measure for retrieval-augmented generation specifically. |
| **[OpenAI Evals](https://github.com/openai/evals)** | OpenAI's open-source framework for evaluating language models on custom tasks. Provides a standardized format for defining eval tasks, running completions against them, and comparing results. Designed around OpenAI's models but can be adapted to other providers. | Teams that want to contribute to or draw on the community eval library, or that need a structured evaluation framework where the standard task format is useful; more suitable for systematic model comparison than for ongoing production monitoring. |
| **Public benchmarks** | [LMSYS Chatbot Arena](https://chat.lmsys.org) provides human preference rankings across models through pairwise comparisons — useful for general capability reference. MMLU (Massive Multitask Language Understanding) tests knowledge breadth across academic domains. MT-Bench evaluates multi-turn instruction following. Domain-specific benchmarks (MedQA for healthcare, FinanceBench for finance) provide more relevant reference points for sector-specific deployments. | Establishing a capability baseline before selecting a model for a new use case; not a substitute for evaluation on your own data and tasks, but a useful starting point for narrowing the candidate model set. |

---

## Vector Databases and Retrieval Infrastructure

Vector databases store and index high-dimensional embeddings — the numerical representations of text, images, or other data — and serve nearest-neighbor queries that power retrieval-augmented generation. This is a rapidly consolidating market: several products have merged, major cloud providers have added vector search to their existing database offerings, and the default choice for many teams is now to start with an extension on their existing relational database before moving to a dedicated vector store.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[pgvector](https://github.com/pgvector/pgvector)** | PostgreSQL extension that adds vector storage and similarity search (cosine, L2, inner product) to existing Postgres databases. Supports approximate nearest-neighbor indexing via HNSW and IVFFlat. No new infrastructure required if you already run PostgreSQL. | The recommended starting point for most teams. If your data volume is under a few tens of millions of vectors and your query latency requirements are not extreme, pgvector on an existing Postgres instance will handle the workload. Move to a dedicated vector database only when you hit real scaling constraints. |
| **[Pinecone](https://www.pinecone.io)** | Managed, serverless vector database designed specifically for production-scale similarity search. Handles indexing, scaling, and infrastructure management as a cloud service. Straightforward API. Strong operational simplicity but fully proprietary and cloud-only. | Teams that need a managed vector database at scale and want to minimize operational overhead; the easiest path to production-scale vector search without running infrastructure, at the cost of vendor lock-in. |
| **[Weaviate](https://weaviate.io)** | Open-source vector database with built-in hybrid search (vector + keyword), multi-tenancy, and modules for automatic vectorization via integrated embedding models. Can be self-hosted or used as a managed cloud service. | Organizations that need hybrid retrieval (semantic + keyword), want to run self-hosted for data residency reasons, or need the multi-tenancy model for serving multiple internal business units from a single cluster. |
| **[Qdrant](https://qdrant.tech)** | Open-source vector search engine with a focus on performance and filtering capabilities. Supports complex payload filtering alongside vector search, enabling precise scoped retrieval. Self-hosted and cloud-managed options. | Use cases where retrieval needs to combine vector similarity with structured metadata filters — for example, retrieving semantically similar documents that also match a date range, department, or access tier. |
| **[Chroma](https://www.trychroma.com)** | Open-source, lightweight vector database designed for local development and embedding in applications. Simple Python-native API with minimal setup. Not designed for production-scale multi-tenant deployments. | Rapid local prototyping and development environments where ease of setup matters more than production scale; a sensible default during early RAG development before the retrieval layer is hardened for production. |

---

## MLOps and Model Registry

Full MLOps tooling — experiment tracking, model registries, data versioning, and model serving — is most relevant for organizations that are fine-tuning or training models, not just consuming APIs. For teams using foundation models via API, the relevant subset is narrower: a model registry to track which version of what model is deployed where, and a serving layer if fine-tuned models are being deployed. This section covers the full stack but calls out what matters at each stage.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[MLflow](https://mlflow.org)** | Open-source platform for experiment tracking, model registry, and deployment. The de facto standard for tracking training runs, logging parameters and metrics, versioning model artifacts, and managing promotion through staging to production. Integrates with most ML frameworks and cloud platforms. | Any organization doing model training or fine-tuning that needs a governed model registry with full lineage — who trained this model, on what data, with what hyperparameters, and who promoted it to production. The most commonly deployed MLOps tool in enterprise environments. |
| **[Weights & Biases](https://wandb.ai)** | Experiment tracking, model registry, and artifact versioning platform. More polished UI than MLflow and stronger on team collaboration features; closed-source with a commercial tier for enterprise features. Widely used in research and ML-engineering-heavy organizations. | Teams where experiment tracking and model comparison across researchers or engineers is the primary workflow; also a good fit where the visualization and reporting quality of the tracking UI matters. |
| **[DVC](https://dvc.org)** (Data Version Control) | Open-source tool for versioning data and ML pipelines using Git-compatible storage. Tracks data files, pipeline definitions, and model artifacts in a version-controlled, reproducible way without storing large files in Git. | Organizations where data versioning and pipeline reproducibility are the primary concern — particularly where datasets are large, change frequently, and need to be tied to specific model versions for compliance or debugging. |
| **[Hugging Face Hub](https://huggingface.co)** | The primary public platform for sharing and downloading pre-trained models, datasets, and model cards. For enterprises, the Hub is also available as a private instance (Hugging Face Enterprise Hub) for hosting proprietary fine-tuned models internally. | Teams that are fine-tuning open-source models and need a collaborative registry for sharing model artifacts; also the natural first stop for evaluating open-source model candidates before fine-tuning or distillation work begins. |
| **[BentoML](https://www.bentoml.com)** | Open-source model serving framework for packaging and deploying ML models as production-ready REST APIs. Handles batching, resource management, and containerization. Well-suited to custom model deployments outside of cloud ML platforms. | Teams deploying custom or fine-tuned models that need portable, containerized serving without committing to a specific cloud ML platform's serving infrastructure. |
| **[Ray Serve](https://docs.ray.io/en/latest/serve/index.html)** | Scalable model serving library built on Ray that supports high-throughput, low-latency model deployments with support for batching, model composition, and multi-model pipelines. Handles the Python-native distributed compute underneath. | Organizations serving models at high request volumes that need fine-grained control over batching and resource allocation; particularly relevant for large model deployments where latency and throughput optimization require more control than managed platforms provide. |

---

## Developer Tooling and Prompt Management

The developer enablement layer covers the tools that AI engineering teams use day-to-day: AI-assisted coding environments that accelerate development, and prompt management systems that bring version control and observability to the prompts that drive production AI applications. As organizations mature their AI platform practice, prompt management typically moves from ad hoc (prompts hardcoded in application code) to a structured discipline with versioning, testing, and deployment workflows.

| Tool | What it does | Best for |
|------|--------------|----------|
| **[GitHub Copilot](https://github.com/features/copilot)** | Microsoft/GitHub's AI coding assistant, integrated into VS Code, JetBrains IDEs, and the GitHub web UI. Provides inline code completion, chat-based code generation, and PR review assistance. Enterprise tier includes policy controls, audit logging, and exclusion of sensitive code from model training. | The default choice for enterprises already on GitHub Enterprise, where license management and SSO integration are handled through existing agreements. Enterprise controls make it appropriate for regulated environments. |
| **[Cursor](https://www.cursor.com)** | AI-first code editor (VS Code fork) with deep LLM integration — inline generation, codebase-aware chat, and multi-file edit capabilities. Faster and more contextually aware than Copilot for complex refactors; requires migration to a new editor. | Engineering teams willing to adopt a new editor for significantly more capable AI assistance, particularly for large-scale refactors, architecture exploration, and tasks that require reasoning across multiple files simultaneously. |
| **[Continue.dev](https://www.continue.dev)** | Open-source AI coding assistant that integrates with VS Code and JetBrains, supporting any LLM backend via LiteLLM or direct API. Gives organizations full control over which model serves code completion requests — including self-hosted models for data sensitivity reasons. | Organizations that need AI coding assistance but cannot send code to external APIs due to data governance requirements; also teams that want to run coding assistance on internal fine-tuned models. |
| **[PromptLayer](https://promptlayer.com)** | See Model Evaluation section above. Also functions as a prompt management platform — versioning prompt templates, tracking which prompt version was used for which requests, and providing a UI for prompt iteration. | Teams that need both prompt management and request logging in a single tool; the eval and management capabilities are reasonably integrated. |
| **[Langfuse](https://langfuse.com)** | Open-source LLM observability and prompt management platform. Provides request tracing, prompt versioning, dataset management for evals, and a self-hostable deployment option. Growing alternative to LangSmith, particularly for teams that want open-source with self-hosting. | Organizations that want LangSmith-like capabilities (tracing, prompt management, eval datasets) without the LangChain dependency or cloud-only deployment model; the open-source and self-hosted option is a differentiator for data-sensitive environments. |
| **Internal prompt template libraries** | Most organizations with mature AI platform practices build internal prompt template libraries — version-controlled repositories of approved prompt patterns, role descriptions, few-shot examples, and system prompt components that teams draw on. These are not off-the-shelf tools; they are maintained as internal engineering assets. | Any team at sufficient scale to benefit from reuse and consistency across AI applications. This is the pattern that tends to emerge organically as organizations move from individual application prompts to a shared platform layer — and it is worth planning for intentionally rather than inheriting inconsistently. |

---

## References

- LangChain — *LangChain documentation and LangGraph documentation*, langchain.com
- LlamaIndex — *LlamaIndex documentation*, docs.llamaindex.ai
- Microsoft — *Semantic Kernel documentation*, learn.microsoft.com/semantic-kernel
- deepset — *Haystack documentation*, haystack.deepset.ai
- Microsoft — *AutoGen documentation*, microsoft.github.io/autogen
- CrewAI — *CrewAI documentation*, docs.crewai.com
- Anthropic — *Tool use documentation for Claude*, docs.anthropic.com
- OpenAI — *Assistants API documentation*, platform.openai.com/docs/assistants
- LiteLLM — *LiteLLM documentation and proxy server guide*, docs.litellm.ai
- PortKey — *AI Gateway documentation*, portkey.ai/docs
- Helicone — *Helicone documentation*, docs.helicone.ai
- Braintrust — *Braintrust documentation*, www.braintrust.dev/docs
- LangSmith — *LangSmith documentation*, docs.smith.langchain.com
- PromptLayer — *PromptLayer documentation*, docs.promptlayer.com
- Weights & Biases — *LLMOps and Prompts documentation*, docs.wandb.ai
- RAGAS — *RAGAS documentation*, docs.ragas.io
- OpenAI — *Evals framework*, github.com/openai/evals
- LMSYS — *Chatbot Arena (LMSYS Leaderboard)*, chat.lmsys.org — human preference rankings across publicly available models
- Hendrycks et al. — *Measuring Massive Multitask Language Understanding* (MMLU), arXiv 2020
- Zheng et al. — *Judging LLM-as-a-Judge with MT-Bench and Chatbot Arena*, NeurIPS 2023
- pgvector — *pgvector: Open-source vector similarity search for Postgres*, github.com/pgvector/pgvector
- Pinecone — *Pinecone documentation*, docs.pinecone.io
- Weaviate — *Weaviate documentation*, weaviate.io/developers/weaviate
- Qdrant — *Qdrant documentation*, qdrant.tech/documentation
- Chroma — *Chroma documentation*, docs.trychroma.com
- MLflow — *MLflow documentation*, mlflow.org/docs
- Weights & Biases — *W&B documentation*, docs.wandb.ai
- DVC — *DVC documentation*, dvc.org/doc
- Hugging Face — *Hugging Face Hub documentation*, huggingface.co/docs/hub
- BentoML — *BentoML documentation*, docs.bentoml.com
- Ray — *Ray Serve documentation*, docs.ray.io/en/latest/serve
- GitHub — *GitHub Copilot documentation*, docs.github.com/copilot
- Cursor — *Cursor documentation*, docs.cursor.com
- Continue.dev — *Continue documentation*, docs.continue.dev
- Langfuse — *Langfuse documentation*, langfuse.com/docs
