---
type: Concept
title: Building Yours Without an Engineer
description: "A design for a team knowledge base with no server and no engineer, built from patterns proven for one person, not yet observed working for a team."
tags: [team-second-brain, practitioner-guide]
timestamp: "2026-07-05"
---

Everything on [The Single-Player Ceiling](/team-second-brain/01-the-single-player-ceiling.md)
either needs someone to run a server or caps out at sharing files, not a person's actual AI
use. This page sketches a third path: no server, no proprietary platform, built from a shared
Git repository and whatever AI tool each person already uses.

**Read this as a design to try, not a proven playbook.** Every individual piece here is real —
Karpathy's own wiki pattern, Claude's GitHub integration, the shared-brain architecture below —
but each is documented at the scale it was actually built for: one person's own knowledge base,
or a released beta with no reported team using it yet
([Rezun & Kapusta, 2026](#ev-rezun-2026-shared-brain-architecture)). No team has been found
running this specific combination past its first weeks. If you try it, you are the pilot — the
honest value of this page is the shape worth testing, not a result to expect.

## Pick a starting point for your team's size and comfort

If nobody on the team has ever used Git, start with a shared folder in whatever cloud drive
the team already uses, and skip straight to the habit in the next section — the folder can
graduate to Git later. If one person is comfortable with Git (most teams have someone), a
private GitHub repository costs nothing at small team sizes and is the sturdier foundation:
version history, no accidental overwrites, and a natural home for the setup below.

## The shape of the design

This borrows the shared-brain architecture released in beta by
[Rezun & Kapusta, 2026](#ev-rezun-2026-shared-brain-architecture) — private by default, built
only from what someone explicitly contributes — and adapts Karpathy's solo wiki-maintenance
pattern to a team's shared repo. Each piece is real and usable today; stringing them together
this way for a team, with anyone actually reporting back on it, is the part nobody has done yet.

1. **Create one shared repository.** A single private Git repo, with one folder of plain
   markdown files. Nothing else lives here — no code, no proprietary format.
2. **Keep using your own AI tool as normal.** Nothing changes about how anyone works day to
   day. The shared repo is not where the thinking happens.
3. **File the good answers, not the whole conversation.** Karpathy's own gist frames this step
   for one person's own wiki: "good answers can be filed back into the wiki as
   new pages... this way your explorations compound in the knowledge base just like ingested
   sources do" ([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-query-compounds)). The idea, ported
   to a team: when a conversation produces something worth the team knowing, ask the assistant
   to turn it into a short markdown page, and add that page to the shared repo. This is the
   step to watch — a human still has to notice, decide, and act, every time, for every person
   on the team, which is the exact habit every abandoned team wiki also assumed would hold.
4. **Point the team's AI tools at the shared repo to answer questions.** Claude's own GitHub
   integration supports this: connect a repository to a shared Project, and "your
   selected content will be added to the project knowledge for Claude to access and
   process" — synced on demand, not automatically, so someone selects sync when the repo has
   moved on ([Anthropic, 2026](#ev-claude-2026-github-integration)). Any tool with a similar
   file or repository connector works the same way.
5. **Health-check the repo on a schedule, not on hope.** Karpathy again, describing his own
   solo practice: "periodically, ask the LLM to health-check the wiki. Look for:
   contradictions between pages, stale claims that newer sources have superseded, orphan pages
   with no inbound links" ([Karpathy, 2026](#ev-karpathy-llm-wiki-2026-lint-loop)). For a team,
   this doubles as the tiebreaker when two people file conflicting pages — surfacing the
   conflict weekly is the mechanism, not a person appointed to resolve it.

## The actual risk: whether the habit survives a busy week

One commenter watching a similar tool launch named the real threat to this design: "the teams
who would benefit most from this are the ones moving fastest and documenting least, which means
they're also the ones least likely to build a new habit around capturing decisions"
([Adin, 2026](#ev-adin-2026-fast-teams-document-least)) — one person's account, not a study, but
it matches the pattern every corporate wiki that ever died also followed: a documentation step
got skipped the moment things got busy. The design below is an attempt to avoid that failure
mode, not proof that it does.

Attach the habit to something that already happens, instead of asking anyone to remember a
new one. End a significant piece of AI-assisted work with one extra question to the
assistant already open: "is this worth adding to the shared wiki?" If yes, that assistant
can draft the page in the same breath. A five-minute slot in an existing weekly meeting
covers the health check — no separate ritual to forget.

## When to graduate to something bigger

This design has an honest ceiling. Search gets slow once the repo holds a few hundred pages
without embeddings. Access control is whatever Git's own permissions give you, nothing
finer. And once someone is hired specifically to keep the repo running, the team has quietly
crossed into needing the engineer this page tried to avoid. At that point,
[The Single-Player Ceiling](/team-second-brain/01-the-single-player-ceiling.md) is where to look
for what comes next.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Dr. Tali Rezun and Dražen Kapusta — *The Shared Brain: When Second Brains Start Thinking Together*, 2026.** Private brains remain private. Shared intelligence is built only from explicit contributions. [View source](https://medium.com/@talirezun/the-shared-brain-when-second-brains-start-thinking-together-0d2ad54413d9){#ev-rezun-2026-shared-brain-architecture} · verified 2026-07-05 · primary
- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** good answers can be filed back into the wiki as new pages... This way your explorations compound in the knowledge base just like ingested sources do. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-query-compounds} · verified 2026-07-05 · primary
- **Anthropic — *Use the GitHub Integration (Claude Help Center)*, 2026.** Your selected content will be added to the project knowledge for Claude to access and process... You can click 'Sync now' to fetch the latest changes from your repository. [View source](https://support.claude.com/en/articles/10167454-use-the-github-integration){#ev-claude-2026-github-integration} · verified 2026-07-05 · primary
- **Andrej Karpathy — *LLM Wiki (personal gist)*, 2026.** Periodically, ask the LLM to health-check the wiki. Look for: contradictions between pages, stale claims that newer sources have superseded, orphan pages with no inbound links... This keeps the wiki healthy as it grows. [View source](https://gist.github.com/karpathy/442a6bf555914893e9891c11519de94f){#ev-karpathy-llm-wiki-2026-lint-loop} · verified 2026-07-05 · primary
- **Ansari Adin (Product Hunt commenter) — *Brief — Product Hunt launch discussion*, 2026.** the teams who would benefit most from this are the ones moving fastest and documenting least, which means they're also the ones least likely to build a new habit around capturing decisions. [View source](https://www.producthunt.com/products/brief-10){#ev-adin-2026-fast-teams-document-least} · verified 2026-07-05 · primary
