---
type: Playbook
title: Meeting Prep
description: "Have your assistant build a one-page brief for your next meeting from the invite, emails, and linked docs."
tags: [ai-playbooks, meetings]
timestamp: "2026-07-01"
---

This playbook has your assistant build a one-page brief for your next meeting. It pulls the invite, the related emails, and any shared docs, then tells you who is in the room, why, and what is still open. Read it in the minute before you walk in.

## When to run it

Run it before a meeting so the user walks in ready. Or run it at the start of the day and prep every meeting on their calendar at once.

## What it needs

Read access to the user's calendar, email, and document storage. Calendar for the invite, email for the back-and-forth, docs for anything shared. Read access is enough. You are gathering and drafting, not sending or changing anything.

## The playbook

1. Identify the target meeting. If the user named one, find it. Otherwise pull the next upcoming meeting on their calendar. If a day was named, list that day's meetings and prep each one.
2. Open the calendar invite. Note the title, date, time, location or link, the full attendee list, and any agenda or description the organizer wrote.
3. For each external attendee, record their name and, where the invite or their email signature shows it, their role and organization. Do not guess a role you cannot see.
4. Search email next. Find recent threads that name the meeting, its subject, or its attendees. Read the latest few messages in each to catch what was decided, promised, or left open.
5. Collect the documents. Check the invite for attached or linked files. Scan the related email threads for shared documents. Search document storage for files whose title matches the meeting topic.
6. Read each relevant document enough to summarize it in a line or two. If a file is long, focus on the summary, decisions, and any section aimed at this meeting.
7. Pull together open questions. Draw them from unanswered email threads, action items with no owner, and gaps between the agenda and what you found.
8. Draft two or three suggested talking points grounded in the background you gathered. Keep them specific to this meeting. Mark anything you inferred rather than read.
9. Assemble a one-page brief: purpose, who is attending and their role, relevant background, open questions, suggested talking points. Note anything you could not find rather than filling the gap.
10. Present the brief to the user. Take no other action.

## What it produces

A one-page brief the user can skim in a minute before they walk in. It names who is in the room and why the meeting exists. It gives what the user needs to know going in, what is still open, and a few things worth raising.

```
Meeting Brief — Q3 Roadmap Sync
Thu, 2:00 PM · Video call

Purpose
Align on Q3 priorities and confirm the launch date for Project Falcon.

Attendees
- Jordan Lee (Product Lead, Acme) — owns the roadmap
- Sam Rivera (Eng Manager, Acme) — flagged the timeline risk
- You

Background
- Last email thread (Mon): Sam raised that the API work may slip two weeks.
- "Falcon Launch Plan" doc: launch pencilled for Aug 12, still marked draft.

Open questions
- Is Aug 12 firm, given the API slip Sam raised?
- Who owns the marketing handoff? No owner in the plan doc.

Suggested talking points
- Ask Sam to size the two-week risk before the date is locked.
- Propose naming a marketing-handoff owner today.

Couldn't find: no notes from the prior roadmap sync.
```

## Guardrails

Read and draft only. Never send a message, reply to a thread, accept or decline the invite, edit a document, or change anything on the user's behalf. The brief is for the user's eyes.

If a thread or document looks sensitive or personal, do not quote it in detail. Flag that it exists and let the user decide.

If two attendees share a name, or a document might be the wrong version, say so rather than guessing. When something is inferred rather than read directly, mark it as such.

## Make it yours

- Ask for a specific length: a tight half-page, or a fuller brief with more background.
- Tell the assistant to weight one source more, like "lean on the email thread, skip old docs."
- For recurring meetings, ask it to lead with what changed since last time.
- Have it flag prep the user still owes: an unanswered question or a promised document.
