---
type: Concept
title: MCP and the Context Gap
description: "What the Model Context Protocol actually standardizes, the gap its own spec admits it leaves open, and why every context-layer vendor pitch is a bet on filling it differently."
tags: [ai-platform, architecture, mcp, agent-infrastructure]
timestamp: "2026-07-08"
---

## Why This Page Exists

Since 2025, a cluster of terms — "context layer," "context engineering," "memory layer," "semantic layer" — has spread across vendor blogs, conference talks, and analyst notes, all describing some version of the same claim: agents need durable, structured access to organizational knowledge, and a new architectural layer is emerging to provide it. The terms are used inconsistently. Some sources treat them as synonyms; others as a stack; a few as competing frameworks. Almost all of the definitional content comes from vendors selling a product that the definition happens to require.

One piece of this discourse is not vendor marketing: the Model Context Protocol (MCP). MCP is a real, dated, specification-governed standard, and its own authors are explicit about what it does and does not solve. Understanding MCP precisely — rather than through the vendor gloss layered on top of it — is the fastest way to cut through the rest of the "context layer" discourse, because MCP marks the actual boundary between settled infrastructure and the still-contested territory vendors are racing to define.

## What MCP Actually Standardizes

MCP is a protocol: a set of message formats and interaction rules, not a product. It runs over [JSON-RPC 2.0](https://www.jsonrpc.org/) between three roles — a **host** (the LLM application), a **client** (a connector inside the host), and a **server** (something that provides context or capabilities). Anthropic introduced it on November 25, 2024, framing the problem it solves in blunt, specific terms: "every new data source requires its own custom implementation, making truly connected systems difficult to scale" ([Anthropic, 2024](#ev-anthropic-2024-mcp-announcement-problem-and-definition)). That is an integration problem — an N-tools-by-M-applications wiring problem — not a claim about memory, meaning, or governance.

The specification (2025-06-18 revision) defines exactly six primitives, three offered by servers and three by clients ([Model Context Protocol, 2025](#ev-mcp-spec-2025-06-18-primitives)):

| Offered by | Primitive | What it is |
|---|---|---|
| Server | **Resources** | Context and data, for the user or the model to use |
| Server | **Prompts** | Templated messages and workflows for users |
| Server | **Tools** | Functions the AI model can execute |
| Client | **Sampling** | Server-initiated agentic behaviors and recursive LLM interactions |
| Client | **Roots** | Server-initiated inquiries into which URI/filesystem boundaries to operate in |
| Client | **Elicitation** | Server-initiated requests for more information from the user |

That table is the entire surface area of the protocol. There is no seventh primitive for memory, no built-in notion of an "entity," and no field for a governance policy. MCP standardizes *how* a host reaches a server and *what shapes* the exchange can take — not what the server remembers, not whether two servers agree on what "customer" means, and not who is allowed to see what.

## The Gap MCP's Own Spec Admits

This isn't a gap you have to infer — the specification says it directly, in its own security section: "While MCP itself cannot enforce these security principles at the protocol level, implementors SHOULD: build robust consent and authorization flows into their applications..." ([Model Context Protocol, 2025](#ev-mcp-spec-2025-06-18-no-protocol-level-security)). Consent, authorization, and access control are left entirely to whoever builds the host and server — the protocol carries no mechanism to enforce any of it.

That quoted sentence is specifically about enforcement — but the protocol's narrow scope leaves two further gaps beyond it. Together, all three map directly onto the three things "context layer" vendors are each independently trying to sell:

- **No persistence.** MCP defines how a server exposes a resource *right now*. It says nothing about whether that server remembers anything about a prior session — that's a memory system, built on top of MCP or independent of it entirely (Mem0, Cognee, Zep, and Redis's Agent Memory component all live here — see [Tooling Landscape](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/03-tooling-landscape.md#memory-and-context-frameworks)).
- **No semantic agreement.** MCP doesn't require two servers to mean the same thing by the same word. If a CRM's "customer" and a billing system's "account" are the same real-world entity, MCP has no primitive that says so — that reconciliation is a semantic/entity-resolution layer, built separately.
- **No enforcement.** As the spec states outright, access control is an implementor responsibility, not a protocol guarantee. A host that connects to ungoverned MCP servers gets exactly the access those servers choose to grant, however that was decided.

## Why MCP Is the One Settled Piece

The rest of the "context layer" discourse deserves real skepticism. The pattern — a durable, unifying layer that will finally give the enterprise one coherent view of its own knowledge — has run before, under other names: master data management, enterprise semantic web and knowledge-graph initiatives, service-oriented integration buses, customer data platforms, data fabric and data mesh. Each wave promised the same outcome and mostly ended the same way: absorbed into ordinary plumbing, fragmented into vendor lock-in, or renamed and re-sold a couple of years later. The current wave shares a tell with its predecessors: one of the most visible voices defining "context layer" is Atlan, a data-catalog vendor whose own guide to the term positions Atlan's product line — an "Enterprise Data Graph," "Context Agents," and a "Context Lakehouse" — as the delivery mechanism for the category it is defining ([Atlan, 2026](#ev-atlan-2026-context-layer-guide-vendor-example)). That is a company defining the category in the shape of the product it sells, not a disqualifying fact on its own, but a reason to read every "context layer" claim with the same question this page is built around: what, specifically, is being added on top of MCP?

MCP is different on one specific, checkable point: it has genuine cross-vendor governance that the earlier waves never achieved. On December 9, 2025, Anthropic donated MCP to the Agentic AI Foundation, a directed fund under the Linux Foundation, co-founded with Block and OpenAI and backed by Google, Microsoft, AWS, Cloudflare, and Bloomberg. At the time of donation, MCP had more than 10,000 active public servers and over 97 million monthly SDK downloads across Python and TypeScript, with adoption across ChatGPT, Cursor, Gemini, Microsoft Copilot, and Visual Studio Code ([Anthropic, 2025](#ev-anthropic-2025-mcp-agentic-ai-foundation-donation)). No prior "unify the enterprise's knowledge" wave had a comparable, neutrally-governed standard sitting underneath it — MDM and CDP were fought over between competing vendors precisely because nothing like MCP existed to settle the transport question first.

A handful of independent academic preprints have also started proposing names and structures for what should sit on top of MCP — a maturity model running prompt engineering through context, intent, and specification engineering ([Vishnyakova, 2026](#ev-vishnyakova-2026-context-engineering-maturity-model)), and a declarative, Kubernetes-inspired governance model for the same gap ([Mouzouni, 2026](#ev-mouzouni-2026-context-kubernetes)). Both are solo-author arXiv preprints, unreviewed — real proposals, not yet a field consensus.

## Reading a "Context Layer" Pitch, Now That You Know This

Once the boundary is clear, a vendor's "context layer" or "context engineering" pitch becomes easy to place. Ask what it's actually claiming to add on top of MCP's six primitives:

- If the pitch is about **remembering things across sessions** — that's a memory-layer claim; see the tools named above.
- If the pitch is about **making different systems agree on what an entity means** — that's a semantic/entity-resolution claim, closer to the metadata and lineage work already covered in [Data Readiness](/enterprise-ai-transformation/tracks/03-data-readiness/index.md).
- If the pitch is about **deciding who can see or change what** — that's a governance and access-control claim, the domain [AI Governance Framework](/enterprise-ai-transformation/tracks/02-ai-governance-and-risk/02-ai-governance-framework.md) already owns.
- If the pitch bundles all three under one new noun and implies you need to buy the whole stack from one vendor to get any of it — treat that framing with the same skepticism this track applies to any single-vendor lock-in claim (see [Common Failure Modes](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/02-technology-architecture-framework.md#common-failure-modes) in the Technology Architecture Framework).

None of the three gaps require abandoning MCP or waiting for the "context layer" category to mature — they're solvable today, piece by piece, on top of a protocol that is already standing on solid, checkable ground. For the current landscape of tools that fill the memory piece specifically, see the [Memory and Context Frameworks](/enterprise-ai-transformation/tracks/04-technology-architecture-and-platform/03-tooling-landscape.md#memory-and-context-frameworks) category in the Tooling Landscape. For the security risk this same connectivity introduces — a different question from what MCP structurally covers — see [Supply Chain and MCP Risk](/ai-assisted-software-development/02-securing-the-coding-workflow/supply-chain-and-mcp-risk.md).

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Anthropic — *Introducing the Model Context Protocol*, 2024-11-25.** Every new data source requires its own custom implementation, making truly connected systems difficult to scale. The Model Context Protocol is an open standard that enables developers to build secure, two-way connections between their data sources and AI-powered tools. [View source](https://www.anthropic.com/news/model-context-protocol){#ev-anthropic-2024-mcp-announcement-problem-and-definition} · verified 2026-07-08 · primary
- **Model Context Protocol — *MCP Specification (2025-06-18 revision)*, 2025-06-18.** Servers offer any of the following features to clients: Resources: Context and data, for the user or the AI model to use. Prompts: Templated messages and workflows for users. Tools: Functions for the AI model to execute. Clients may offer the following features to servers: Sampling: Server-initiated agentic behaviors and recursive LLM interactions. Roots... Elicitation... [View source](https://modelcontextprotocol.io/specification/2025-06-18){#ev-mcp-spec-2025-06-18-primitives} · verified 2026-07-08 · primary
- **Model Context Protocol — *MCP Specification (2025-06-18 revision) — Security and Trust & Safety*, 2025-06-18.** While MCP itself cannot enforce these security principles at the protocol level, implementors SHOULD: Build robust consent and authorization flows into their applications... [View source](https://modelcontextprotocol.io/specification/2025-06-18){#ev-mcp-spec-2025-06-18-no-protocol-level-security} · verified 2026-07-08 · primary
- **Atlan — *Context Layer for AI Agents: Enterprise Guide 2026*, 2026-05-08 (published), updated 2026-06-30.** the de facto standard for connecting agents to tools (referring to MCP). Atlan's own guide names its product line — Enterprise Data Graph, Context Agents, Context Lakehouse — as the delivery mechanism for the context layer it describes. [View source](https://atlan.com/know/context-layer-for-ai-agents/){#ev-atlan-2026-context-layer-guide-vendor-example} · verified 2026-07-08 · primary
- **Anthropic — *Donating the Model Context Protocol and establishing the Agentic AI Foundation*, 2025-12-09.** co-founded by Anthropic, Block and OpenAI, with support from Google, Microsoft, Amazon Web Services (AWS), Cloudflare, and Bloomberg... more than 10,000 active public MCP servers... 97M+ monthly SDK downloads across Python and TypeScript... adopted by ChatGPT, Cursor, Gemini, Microsoft Copilot, Visual Studio Code. [View source](https://www.anthropic.com/news/donating-the-model-context-protocol-and-establishing-of-the-agentic-ai-foundation){#ev-anthropic-2025-mcp-agentic-ai-foundation-donation} · verified 2026-07-08 · primary
- **Vishnyakova, V.V. (independent arXiv preprint author) — *Context Engineering: From Prompts to Corporate Multi-Agent Architecture (arXiv:2603.09619)*, 2026.** whoever controls the agent's context controls its behavior; whoever controls its intent controls its strategy; whoever controls its specifications controls its scale. [View source](https://arxiv.org/abs/2603.09619){#ev-vishnyakova-2026-context-engineering-maturity-model} · verified 2026-07-08 · primary
- **Mouzouni, C. (independent arXiv preprint author) — *Context Kubernetes: Declarative Orchestration of Enterprise Knowledge for Agentic AI Systems (arXiv:2604.11623)*, 2026.** establishes a three-tier permission model ensuring agent authority remains subordinate to human authority... Formal verification using TLA+ model-checking confirms safety across millions of states. [View source](https://arxiv.org/abs/2604.11623){#ev-mouzouni-2026-context-kubernetes} · verified 2026-07-08 · primary
