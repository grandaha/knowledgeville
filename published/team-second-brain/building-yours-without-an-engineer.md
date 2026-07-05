---
type: Concept
title: Building Yours Without an Engineer
description: "How a non-technical small team actually sets up and keeps alive a shared team knowledge base."
tags: [team-second-brain, practitioner-guide]
timestamp: "2026-07-05"
---

Everything on [The Single-Player Ceiling](/team-second-brain/the-single-player-ceiling.md)
either needs someone to run a server or caps out at sharing files, not a person's actual AI
use. This page covers a third path: no server, no proprietary platform, built from a shared
Git repository and whatever AI tool each person already uses.

## Pick a starting point for your team's size and comfort

If nobody on the team has ever used Git, start with a shared folder in whatever cloud drive
the team already uses, and skip straight to the habit in the next section — the folder can
graduate to Git later. If one person is comfortable with Git (most teams have someone), a
private GitHub repository costs nothing at small team sizes and is the sturdier foundation:
version history, no accidental overwrites, and a natural home for the setup below.

## A concrete setup walkthrough

This setup follows the shared-brain architecture described in
[Rezun & Kapusta, 2026](#ev-rezun-2026-shared-brain-architecture): each person's own AI use
stays exactly as private as it is today, and the shared layer holds only what someone
explicitly decides to add.

1. **Create one shared repository.** A single private Git repo, with one folder of plain
   markdown files. Nothing else lives here — no code, no proprietary format.
2. **Keep using your own AI tool as normal.** Nothing changes about how anyone works day to
   day. The shared repo is not where the thinking happens.
3. **File the good answers, not the whole conversation.** Karpathy's own framing of this
   step: "good answers can be filed back into the wiki as new pages... this way your
   explorations compound in the knowledge base just like ingested sources do"
   ([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-query-compounds)). When a conversation
   produces something worth the team knowing, ask the assistant to turn it into a short
   markdown page, and add that page to the shared repo. That is the one deliberate,
   explicit act of contribution — everything else about a person's AI use stays private.
4. **Point the team's AI tools at the shared repo to answer questions.** Claude's own GitHub
   integration does this directly: connect a repository to a shared Project, and "your
   selected content will be added to the project knowledge for Claude to access and
   process" — synced on demand, not automatically, so someone selects sync when the repo has
   moved on ([Anthropic, 2026](#ev-claude-2026-github-integration)). Any tool with a similar
   file or repository connector works the same way.
5. **Health-check the repo on a schedule, not on hope.** Karpathy again: "periodically, ask
   the LLM to health-check the wiki. Look for: contradictions between pages, stale claims
   that newer sources have superseded, orphan pages with no inbound links"
   ([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-lint-loop)). Once a week is enough for a
   small team's contribution volume.

## Making it a habit instead of a chore

A real risk this bundle's research surfaced: "the teams who would benefit most from this are
the ones moving fastest and documenting least, which means they're also the ones least likely
to build a new habit around capturing decisions"
([Adin, 2026](#ev-adin-2026-fast-teams-document-least)). A separate documentation step gets
skipped the moment things get busy — so this setup does not create one.

Attach the habit to something that already happens, instead of asking anyone to remember a
new one. End a significant piece of AI-assisted work with one extra question to the
assistant already open: "is this worth adding to the shared wiki?" If yes, that assistant
can draft the page in the same breath. A five-minute slot in an existing weekly meeting
covers the health check — no separate ritual to forget.

## When to graduate to something bigger

This setup has an honest ceiling. Search gets slow once the repo holds a few hundred pages
without embeddings. Access control is whatever Git's own permissions give you, nothing
finer. And once someone is hired specifically to keep the repo running, the team has quietly
crossed into needing the engineer this page was written to avoid. At that point,
[The Single-Player Ceiling](/team-second-brain/the-single-player-ceiling.md) is where to look
for what comes next.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Dr. Tali Rezun and Dražen Kapusta — *The Shared Brain: When Second Brains Start Thinking Together*, 2026.** Private brains remain private. Shared intelligence is built only from explicit contributions. [View source](https://medium.com/@talirezun/the-shared-brain-when-second-brains-start-thinking-together-0d2ad54413d9){#ev-rezun-2026-shared-brain-architecture} · verified 2026-07-05 · primary
- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** good answers can be filed back into the wiki as new pages... This way your explorations compound in the knowledge base just like ingested sources do. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-query-compounds} · verified 2026-07-05 · primary
- **Anthropic — *Use the GitHub Integration (Claude Help Center)*, 2026.** Your selected content will be added to the project knowledge for Claude to access and process... You can click 'Sync now' to fetch the latest changes from your repository. [View source](https://support.claude.com/en/articles/10167454-use-the-github-integration){#ev-claude-2026-github-integration} · verified 2026-07-05 · primary
- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** Periodically, ask the LLM to health-check the wiki. Look for: contradictions between pages, stale claims that newer sources have superseded, orphan pages with no inbound links... This keeps the wiki healthy as it grows. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-lint-loop} · verified 2026-07-05 · primary
- **Ansari Adin (Product Hunt commenter) — *Brief — Product Hunt launch discussion*, 2026.** the teams who would benefit most from this are the ones moving fastest and documenting least, which means they're also the ones least likely to build a new habit around capturing decisions. [View source](https://www.producthunt.com/products/brief-10){#ev-adin-2026-fast-teams-document-least} · verified 2026-07-05 · primary
