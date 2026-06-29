---
type: Playbook
title: Turn Messy Notes into a Table
description: Convert a pile of notes into a clean, structured table.
tags: [data, tables]
timestamp: "2026-06-24"
---

## When to use this

You have a scattered list of notes, ideas, or bullet points and you need them organized so you can compare, sort, or share them. This works well after a meeting, a brainstorm session, or any time your notes feel like a pile rather than a plan.

## The prompt

```
You are a data organizer. I have a set of notes below and I want you to turn them into a clean table.

Steps:
1. Read through all the notes and identify the key categories or fields (for example: Name, Date, Action, Owner).
2. Create a markdown table with one row per item and a column for each field you identified.
3. Fill in each cell using only what's in the notes — do not guess or invent information. If a field is missing for an item, leave that cell blank.
4. After the table, list any items you weren't sure how to categorize.

Here are my notes:
[PASTE YOUR NOTES HERE]
```

## Before and after

**Before** — raw notes from a planning call:

- Sarah will follow up with the vendor by Thursday
- Need to book the conference room for the 14th, Tom owns this
- Budget approval still pending — finance team
- Dev environment setup, no owner yet, should be done before end of month

**After** — what the AI returns:

| Task | Owner | Due Date | Status |
|---|---|---|---|
| Follow up with vendor | Sarah | Thursday | |
| Book conference room | Tom | 14th | |
| Budget approval | Finance team | | Pending |
| Dev environment setup | | End of month | |

## Make it yours

- Add "add a Priority column (High / Medium / Low) based on the urgency implied in the notes" to the prompt.
- Ask it to sort the table by due date or owner after building it.
- If your notes are in a specific format (email thread, Slack dump), tell it: "these are messages from a Slack channel."
- Ask it to output CSV instead of a markdown table if you're pasting into a spreadsheet.

## Watch out for

The AI will occasionally merge two separate items into one row, or split one item into two. Skim the table against your original notes before sharing it. Also, it can only assign an owner if the name appears in your notes; it will not infer who should own something.
