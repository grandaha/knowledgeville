---
type: Concept
title: How to Run These Playbooks
description: "What an agent-executable playbook is, how to hand one to your assistant, and the read-first guardrails they all share."
tags: [ai-playbooks, agents]
timestamp: "2026-07-01"
---

Most of the AI recipes people share are prompts you paste. You do the work; the assistant helps with one step. A playbook is different. It is a whole procedure your assistant runs on its own — reading your tools, doing the work, and handing you the result. This page explains how to run one and what keeps it safe.

## What an agent-executable playbook is

A playbook is written for your assistant to follow, not just for you to read. It says what to do, in order, in plain steps: read this, pull that, sort them, draft the output. You hand the page to an AI assistant that can reach your email and calendar, and it works through the steps.

That is the shift these are built around. Instead of you running the assistant one prompt at a time, the assistant runs the playbook. Your job moves from doing the steps to checking the result. It is the same idea behind [knowledge written for agents](/open-knowledge-format/02-the-potential/01-knowledge-for-agents.md): when the reader is a machine, the instructions have to carry everything it needs.

## How to run one

You need an AI assistant connected to the tools the playbook uses — usually your email and calendar. Most mainstream assistants support this through connectors that can read a connected inbox and calendar. Check whether the one you use offers it. Then it is three steps:

1. **Connect your tools.** Give the assistant read access to your email and calendar. Read access is enough; you do not need to let it send or change anything.
2. **Hand it the playbook.** Paste the playbook into the chat, or point your assistant at this page. The steps are written for it to follow directly.
3. **Review what it gives back.** The assistant does the reading and drafting. You get a finished result — a plan, a triaged inbox, a brief — and you decide what to do with it.

## The shape they all share

Every playbook here follows the same layout, so once you have run one you can run any of them:

- **When to run it** — the trigger, like each weekday morning, or on demand.
- **What it needs** — the tools and access required.
- **The playbook** — the numbered steps the assistant follows.
- **What it produces** — the output, with an example.
- **Guardrails** — the limits the assistant must respect.
- **Make it yours** — how to adjust it to your work.

## The one rule: read-first

Every playbook here is read-first, and that is deliberate. The assistant reads your email and calendar and drafts a result, but it does not send, reply, delete, archive, or accept anything on your behalf. If something looks urgent, sensitive, or unclear, the playbook tells it to flag the item for you rather than act on it.

That keeps you in control. The worst a read-first playbook can do is show you the wrong summary, which you catch in the review step. Nothing leaves your outbox and nothing gets deleted without you. When you are ready to let an assistant take an action — send a reply, book a slot — that is a bigger decision. These playbooks leave it to you.
