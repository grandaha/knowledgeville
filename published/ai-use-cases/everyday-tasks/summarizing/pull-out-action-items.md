---
type: Playbook
title: Pull Out Action Items
description: Extract the to-dos and decisions from notes or a transcript.
tags: [summarizing, action-items]
timestamp: "2026-06-24"
---

## When to use this

You have meeting notes, a call transcript, or a messy email thread, and you need to know: who said they'd do what, and by when? Use this to turn a wall of text into a clean list you can actually act on.

## The prompt

```
You are a meticulous project coordinator. I'm going to paste meeting notes or a transcript below.

Please extract:
1. **Action items** — one per line, in the format: [Person responsible] · [What they will do] · [Deadline, if mentioned]
2. **Decisions made** — brief bullet list of anything the group agreed on
3. **Open questions** — things that came up but weren't resolved

If a person's name isn't clear, use a description like "the facilitator" or "the sales lead."
If no deadline was mentioned for an action item, write "no deadline set."

Do not add items that weren't in the text. If a category has nothing, write "None."

Here are the notes:

[PASTE YOUR NOTES OR TRANSCRIPT HERE]
```

## Before and after

**Before:** A block of rough meeting notes from a 45-minute product review:

> "Sara said she'd look into the API rate limits by end of week. Tom needs to send the updated specs to the dev team — he mentioned Thursday. We agreed to push the launch to Q3. Still unclear whether we need legal sign-off on the new data fields. Marcus is going to check with compliance, no specific date given."

**After:**

> **Action items:**
> - Sara · Research API rate limits · Friday
> - Tom · Send updated specs to dev team · Thursday
> - Marcus · Check with compliance re: new data fields · No deadline set
>
> **Decisions made:**
> - Launch pushed to Q3
>
> **Open questions:**
> - Whether legal sign-off is required for the new data fields

## Make it yours

- **Slack or email thread:** Paste the whole thread and ask it to pull items from everyone's messages.
- **Owner focus:** Add "Only show items assigned to [your name]" to filter the list.
- **Formatted output:** Ask for a markdown table with columns: Owner | Task | Deadline | Status (set all to "open").
- **Follow-up email draft:** After getting the list, say "Now draft a short follow-up email to the team recapping these items."

## Watch out for

AI can only find what's written down. If someone said they'd "handle it" without specifics, AI will flag it vaguely — you'll need to clarify ownership yourself. Also check for implied commitments ("I'll circle back") that the AI might miss or misread as firm action items.
