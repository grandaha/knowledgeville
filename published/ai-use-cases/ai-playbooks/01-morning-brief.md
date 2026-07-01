---
type: Playbook
title: Morning Brief
description: "Have your assistant read your email and calendar and hand you a prioritized plan for the day."
tags: [ai-playbooks, daily]
timestamp: "2026-07-01"
---

This playbook has your assistant turn your inbox and calendar into a plan for the day. It reads what is on today and what came in overnight, then hands you a short, prioritized brief. It is the simplest playbook here, and the template the others follow.

## When to run it

Run this each weekday morning, before the user starts work.

## What it needs

Read access to the user's calendar and email. That is enough — you only read and draft here. You will pull today's calendar events and the email that arrived since yesterday evening. No send, edit, or delete access is required.

## The playbook

1. Read today's events from the user's calendar, from now until end of day. Note the time, title, attendees, and any location or video link for each.
2. Read the user's email received since 6pm yesterday. Focus on unread and flagged messages. Skip obvious newsletters, receipts, and automated notifications.
3. For each meeting, decide if it needs prep. It needs prep if the user is the organizer, if there is an agenda or attached document, or if a linked email thread is unresolved. Note what the prep is in one short line.
4. For each email from a real person that asks a question or expects a reply, capture three things. Who it is from, the subject, and what they want.
5. Look for anything time-sensitive across both: a deadline today, a meeting starting soon, a message marked urgent. Set these aside to call out first.
6. Draft the top three to five priorities for the day. Base them on deadlines, meeting prep, and emails that cannot wait. Keep each to one line.
7. Find the open gaps between meetings that are 45 minutes or longer. Suggest one focus block per gap, matched to a priority from step 6.
8. Assemble the brief in this order: priorities, then today's meetings with prep flags, then emails needing a reply, then suggested focus blocks. Keep it scannable.
9. Present the brief to the user. Take no other action — do not reply to anything, do not add calendar events, do not mark anything read.

## What it produces

A short, scannable plan for the day: a few priorities up top, then meetings, replies to write, and focus blocks. It is meant to be read in under a minute.

```
Morning brief — Tuesday, Mar 4

Top priorities
1. Finish Q2 budget draft (due today, 5pm)
2. Prep for 2pm client review — read their brief first
3. Reply to Sam about the vendor contract

Today's meetings
- 10:00  Team standup
- 14:00  Client review with Acme  ⚑ needs prep: read the brief they sent Monday
- 16:30  1:1 with Priya

Emails to reply to
- Sam Ortiz — "Vendor contract — need your OK by Wed"
- Jordan Lee — "Can you review the deck?"

Suggested focus blocks
- 10:30–12:00  Q2 budget draft
- 15:00–16:00  Deck review for Jordan
```

## Guardrails

You read and draft only. Never send, reply to, delete, archive, or mark anything as read. Never accept, decline, or create calendar events. Never change anything on the user's behalf.

If something looks urgent, sensitive, or unclear, flag it for the user and let them decide. That includes a message that reads as a crisis, a legal or personal matter, or a deadline you cannot confirm. Do not guess. Respect private data: keep the brief with the user and do not repeat message contents anywhere else.

## Make it yours

- Tell the assistant how you rank priorities — deadlines first, or the people you most want to keep happy.
- Change what counts as an email worth flagging. Include your boss and top clients by name, or ignore whole senders.
- Set your own focus-block length and how many the assistant suggests.
- Move the trigger. Run it Sunday night for a week-ahead view, or after lunch for an afternoon reset.
