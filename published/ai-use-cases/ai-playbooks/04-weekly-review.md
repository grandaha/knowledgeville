---
type: Playbook
title: Weekly Review
description: "Have your assistant summarize your week and set up next week's priorities from your calendar and sent mail."
tags: [ai-playbooks, weekly]
timestamp: "2026-07-01"
---

This playbook has your assistant close out your week and start the next one. It reads the week's calendar and your sent mail, tells you what moved and what slipped, then drafts next week's priorities for you to confirm.

## When to run it

Run it Friday afternoon to close the week, or Monday morning to open it. Or any week where the days blurred together and you are not sure what got done.

## What it needs

- Read access to the user's calendar (this week's events).
- Read access to the user's sent mail (what they sent this week).
- A task list is a nice-to-have. If one is connected, read it for open items. Read access is enough for all of this. You will not change anything.

## The playbook

1. Work out the date range for the week just ending: the most recent Monday through today. State the exact dates you are using so the user can catch an off-by-one.
2. Read this week's calendar events across that range. Note the meetings, their titles, and who was in them. Skip declined events and all-day blocks that are not real commitments.
3. Read the user's sent mail across the same range. For each thread, note who it went to and what it was about. This is your record of what the user pushed forward.
4. Group the week into themes. Cluster meetings and sent mail by project, person, or topic. A "1:1 with Priya" plus three emails to Priya is one thread of work, not four.
5. Build the "what happened" recap from those themes. Under each theme, list what moved: decisions made, things shipped, questions answered.
6. Find what slipped. Look for meetings with no follow-up sent, threads where the user was mid-conversation, and questions asked of the user that their sent mail never answered. Flag these plainly; do not guess at why.
7. If a task list is connected, read it. Note items still open, and any that were due this week and were not completed.
8. Now look forward. From the slipped items, the open threads, and anything on next week's calendar, draft a short list of priorities for next week. Keep it to five or six. Order them by what seems most pressing, but say the ordering is a guess.
9. Assemble the recap and the draft priorities into one summary. Keep it skimmable: themes, what slipped, next week's draft list.
10. Present the summary to the user. Ask them to confirm or reshuffle the priorities. Take no other action.

## What it produces

A two-part summary: a look back at the week, and a draft look forward. The recap is grouped by theme, the forward list is a handful of priorities the user can confirm or edit. Nothing is sent or scheduled.

```
Weekly Review — Mon Jun 23 to Fri Jun 27

THIS WEEK
Acme renewal
  - Pricing call Tue; agreed to a 2-year term
  - Sent revised quote to dana@acme.example Thu
Hiring (backend role)
  - 2 screens done; sent feedback to recruiting
Team 1:1s
  - Met with Priya, Sam, and Lee

SLIPPED / UNANSWERED
  - Jordan asked for the Q3 forecast Mon — no reply sent yet
  - Design review booked Wed, but no notes or follow-up went out
  - Task "Draft offsite agenda" was due Thu, still open

NEXT WEEK — DRAFT (please confirm)
  1. Reply to Jordan with the Q3 forecast
  2. Send design review follow-up
  3. Close out the Acme renewal paperwork
  4. Draft the offsite agenda
  5. Finish the two remaining backend screens
```

## Guardrails

- Read and draft only. Never send a reply, and never answer a slipped thread for the user. Never mark a task done, and never create, move, or delete a calendar event. You surface the work; the user acts on it.
- The next-week list is a draft. Present it as a suggestion to confirm, not a plan you have committed to.
- When you cannot tell if something slipped or was just handled elsewhere, say so. Flag it as "looks unanswered — check?" rather than stating it as fact.
- Respect private data. If a meeting or thread looks personal, you can note it exists without repeating its contents.

## Make it yours

- Shift the trigger: run it Sunday evening if that is when you plan, or month-end for a longer look back.
- Add a source: if your notes or docs live somewhere connected, fold in what you finished there too.
- Change the lookback: a two-week range after time off, or just yesterday for a daily version.
- Tune the priority count: ask for a top three if five feels like too much.
