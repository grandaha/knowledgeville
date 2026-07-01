---
type: Playbook
title: End-of-Day Wrap
description: "Have your assistant recap what got done and carry what slipped into tomorrow."
tags: [ai-playbooks, daily]
timestamp: "2026-07-01"
---

This playbook has your assistant close out your day. It reads today's calendar and sent mail, and reconciles what got done against what you planned. Then it hands you a short wrap with a carry-over list for tomorrow. It closes the day the Morning Brief opened.

## When to run it

Run this at the end of your workday, when you are ready to close out.

## What it needs

Read access to your calendar and your sent mail for today. If you keep a task list, read access to that too. Reading is enough — this playbook never writes anything back.

## The playbook

1. Establish "today" in the user's local time zone. Set the window to today from midnight to now.
2. Read today's calendar events. Note each meeting's title, time, and whether it has ended.
3. Read the user's sent mail from today. For each message, note who it went to and the one-line gist.
4. If a task list is connected, read today's tasks: what is marked done, what is still open, and anything overdue.
5. Reconcile the day against the plan. Match sent mail and completed tasks to the meetings and intentions on the calendar.
6. Sort what you found into three buckets: **done** (finished today), **open** (started or planned but not finished), and **carry-over** (should move to tomorrow).
7. For each carry-over item, note why it is carrying — waiting on a reply, ran out of time, blocked, or not started.
8. Flag anything that looks time-sensitive for tomorrow: a deadline, a reply someone is waiting on, an early meeting.
9. Write a short wrap: two or three lines on how the day went, then the three buckets, then the carry-over list.
10. Present the wrap to the user. Take no other action — do not send, reschedule, or create anything.

## What it produces

A short written wrap of your day, split into what got done, what is still open, and what carries into tomorrow. Each carry-over says why it is carrying.

```
End-of-Day Wrap — Tue, Jul 1

Solid day. Cleared the review backlog, but the budget draft
slipped again. Two things need you first thing tomorrow.

Done
- Shipped the Q3 review notes to Priya
- Replied to the vendor about the contract dates
- Closed 3 tickets in the tracker

Open
- Budget draft — got through 2 of 5 sections

Carry into tomorrow
- Finish budget draft (ran out of time) — before the 10am sync
- Reply to Marcus re: hiring plan (waiting on your call)
- Book the offsite venue (not started)
```

## Guardrails

Read and draft only. Never send, reply, delete, or archive anything. Do not create, complete, or reschedule tasks. Do not add or change calendar events. The wrap is a summary you hand over.

If something is ambiguous — a meeting with no clear outcome, a task you cannot tell is done — flag it and ask, do not guess. Treat mail and task contents as private; keep them in the wrap, not anywhere else.

## Make it yours

- Tell it to group carry-overs by project or by person instead of one flat list.
- Ask for a one-line "biggest win" and "biggest snag" at the top.
- Have it draft (not send) tomorrow's top three priorities from the carry-over list.
- Narrow the sent-mail scan to a specific account or label if you run several.
