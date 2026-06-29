---
type: Playbook
title: Compare Options in a Table
description: Lay out choices side by side on the criteria that matter.
tags: [decisions, comparison]
timestamp: "2026-06-24"
---

## When to use this

You're choosing between two or more options: tools, vendors, plans, job offers. You want to see them side by side, without the comparison getting muddled in your head.

## The prompt

```
You are a clear-headed analyst helping me make a decision. I need to compare [OPTIONS — e.g. "three project management tools: Notion, Asana, and Trello"] against the criteria that matter most to me.

My criteria are: [LIST YOUR CRITERIA — e.g. "ease of use, cost, collaboration features, mobile experience"]

Here is any relevant context: [PASTE NOTES, REQUIREMENTS, OR CONSTRAINTS]

Please produce a comparison table with one row per option and one column per criterion. After the table, write 2–3 sentences summarizing which option looks strongest for my situation and why. Do not advocate — just tell me what the table shows.
```

## Before and after

**Before** — what you bring to the prompt:

- Comparing Zoom, Google Meet, and Microsoft Teams
- Care about: free tier limits, screen sharing quality, ease of joining for guests, recording storage
- Team is mostly non-technical; some members are on mobile

**After** — what the AI returns (excerpt):

| | Zoom | Google Meet | Microsoft Teams |
|---|---|---|---|
| Free tier limits | 40 min group calls | Unlimited 1:1, 60 min groups | Unlimited with Microsoft account |
| Screen sharing | Excellent | Good | Good |
| Guest join ease | Link, no account needed | Link, Google account optional | Link, no account needed |
| Recording storage | Cloud (paid) / local | Google Drive | SharePoint / OneDrive |

*"For a non-technical team prioritizing guest ease and no time limits, Google Meet or Teams edges out Zoom on the free tier. If recording to a shared drive matters, Teams integrates most naturally with Microsoft 365."*

## Make it yours

- Add a "weight" column (High / Medium / Low importance) and ask the AI to factor that in.
- Ask for a second table ranking each option per criterion on a 1–3 scale for a quick visual scan.
- Tell the AI which option you're currently leaning toward and ask it to steelman the alternatives.
- After the table, ask: "What's the one thing this table doesn't show that I should still consider?"

## Watch out for

The AI may state specifics — prices, feature limits, version numbers — as facts. These details go stale and are sometimes wrong. Use the table as a thinking frame, then verify any load-bearing detail on each vendor's own site before deciding.
