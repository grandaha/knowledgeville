---
type: Concept
title: The Single-Player Ceiling
description: "What's actually been built on the LLM Wiki pattern so far — real, popular, and every one of them single-user."
tags: [team-second-brain, llm-wiki, tooling-landscape]
timestamp: "2026-07-05"
---

If your team wants to try one of these today, here is what actually exists, what it costs,
and what it genuinely shares across people. This page is a decision aid, not a fresh case
for the gap — [The Team Second Brain](/team-second-brain/the-team-second-brain.md) already
makes that case. Every option below is real, and every one has a self-serve path a small
team could set up this week — except where noted below.

## Self-hosted: free, but someone sets it up

- **AnythingLLM** — open-source (MIT), free to run via Docker. Built for multiple users from the start: a document embedded once becomes available to everyone in the workspace, with role-based access. A managed cloud option exists too. It runs $50 a month under five seats, or $99 a month for the Pro tier ([AnythingLLM, 2026](#ev-anythingllm-2026-pricing)).
- **Onyx** (formerly Danswer) — open-source (MIT), self-hostable, indexes connected tools such as Slack, Confluence, GitHub, and Drive into one shared, searchable corpus. A managed cloud plan runs $20 a user a month, with no stated seat minimum ([Onyx, 2026](#ev-onyx-2026-pricing)).
- **Khoj** — open-source, free to self-host, built as "your AI second brain." The individual version is genuinely free. The team version exists but carries no public price — it is sales-gated, the one part of Khoj that is not self-serve ([Khoj, 2026](#ev-khoj-2026-team-sales-gated)).
- The raw implementations of Andrej Karpathy's own LLM Wiki pattern — projects such as
  nashsu/llm_wiki and AgriciDaniel/claude-obsidian — are free, open, and well built. Every one
  of them is scoped to a single person's own machine and accounts. None adds a second user.

## Accessible SaaS: no setup, still one person at a time

- **Claude Team** runs $25 a user a month monthly, or $20 annual, self-serve for 5 to 150 seats ([Claude, 2026](#ev-claude-team-2026-pricing)). A Project's uploaded files and instructions are genuinely shared across every member with access. Whether one person's own chat history feeds that shared knowledge is a separate question the product does not answer.
- **ChatGPT Business** runs $20 to $25 a user a month, self-serve, with a two-seat minimum ([ChatGPT, 2026](#ev-chatgpt-business-2026-pricing)). A Project shares a knowledge base and a memory across its members. A Custom GPT does not. One person configures it, and everyone else draws on that same fixed setup. Nothing anyone else does with it feeds back into what the GPT knows.
- **Notion AI** requires its Business tier, at $20 to $24 a month, for the full AI feature set ([Notion, 2026](#ev-notion-ai-2026-business-pricing)). It answers by searching the team's already-written wiki pages. It shares what people chose to type up, not what anyone actually asked the AI on the way there.
- **Obsidian** — Sync ($4 to $5 a user a month) supports a shared vault, with no real-time co-editing ([Obsidian, 2026](#ev-obsidian-sync-2026-pricing)). Its most popular AI plugin, Smart Connections, is free and genuinely useful,
  but built and described as one person's tool.

## Where every one of them stops

All eight options share the same limit: each compounds a document, a project, or a folder
someone chose to save — never a person's ongoing use of AI itself.

| Option | Type | Price | What actually compounds |
| --- | --- | --- | --- |
| AnythingLLM | Self-hosted | Free; $50-$99/mo cloud option | Every embedded document, across the whole workspace |
| Onyx | Self-hosted | Free; $20/user/mo managed | Everything indexed from connected tools |
| Khoj | Self-hosted | Free; team tier needs a sales call | Nothing beyond one person, without that call |
| Karpathy-pattern repos | Self-hosted | Free | Nothing — single-user by design |
| Claude Team | SaaS | $20-25/user/mo | A Project's own files and instructions |
| ChatGPT Business | SaaS | $20-25/user/mo | A Project's knowledge base and memory, not a Custom GPT |
| Notion AI | SaaS | $20-24/mo (Business) | Team wiki pages someone already wrote |
| Obsidian + Sync | SaaS add-on | $4-5/user/mo | A shared vault, no real-time co-editing |

[Building Yours Without an Engineer](/team-second-brain/02-building-yours-without-an-engineer.md)
picks a starting point from this table and covers what it actually takes to run it.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **AnythingLLM — *AnythingLLM Pricing*, 2026.** Basic $50/mo, for teams of less than 5 users; Pro $99/mo. [View source](https://anythingllm.com/pricing){#ev-anythingllm-2026-pricing} · verified 2026-07-05 · primary
- **Onyx — *Onyx Pricing*, 2026.** $20 per user/month. [View source](https://onyx.app/pricing){#ev-onyx-2026-pricing} · verified 2026-07-05 · primary
- **Khoj — *Khoj Teams (product page)*, 2026.** tell them about what you're looking for, how big your team is, and what your needs are. [View source](https://khoj.dev/teams){#ev-khoj-2026-team-sales-gated} · verified 2026-07-05 · ⚠ secondary mirror
- **Anthropic — *Claude Pricing*, 2026.** $25/person/month billed monthly, $20/person/month billed annually. [View source](https://claude.com/pricing){#ev-claude-team-2026-pricing} · verified 2026-07-05 · primary
- **OpenAI — *ChatGPT Business Pricing*, 2026.** $20/user/month on an annual plan or $25/user/month monthly, with a 2-seat minimum. [View source](https://openai.com/chatgpt/business/){#ev-chatgpt-business-2026-pricing} · verified 2026-07-05 · ⚠ secondary mirror
- **Notion — *Notion Pricing*, 2026.** Business: $20/mo per member billed annually, $24/mo per member billed monthly. [View source](https://www.notion.com/pricing){#ev-notion-ai-2026-business-pricing} · verified 2026-07-05 · primary
- **Obsidian — *Obsidian Pricing*, 2026.** Sync: $4/mo billed annually, $5/mo billed monthly. [View source](https://obsidian.md/pricing){#ev-obsidian-sync-2026-pricing} · verified 2026-07-05 · primary
