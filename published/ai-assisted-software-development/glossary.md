---
type: Reference
title: Glossary
description: Plain-language definitions of the terms used across this bundle.
tags: [glossary, reference]
timestamp: "2026-07-06"
appendix: true
---

Plain-language definitions of the terms this bundle uses. It grows as the bundle does.

**AI coding agent** — an AI tool that reads a codebase, plans multi-step changes, and
writes or edits files directly, as distinct from an autocomplete-style suggestion tool.
Claude Code, Cursor, and GitHub Copilot's agent modes are examples.

**Agent config file** — a file an AI coding agent reads automatically to get instructions
or context (e.g. `CLAUDE.md`, `.cursorrules`). Because these load without the developer
re-reading them each session, they are a real, documented attack surface — see
[The Real Attack Surface](/ai-assisted-software-development/02-securing-the-coding-workflow/the-real-attack-surface.md).

**Prompt injection** — getting an AI system to follow instructions hidden in content it
processes (a file, a webpage, a tool result) rather than the instructions its actual user
gave it.
