---
type: Playbook
title: Turn a Finance Deck into a One-Page Read
description: Compress a long finance deck into a one-page read you can act on.
tags: [finance-performance, recipe]
timestamp: "2026-06-28"
---

## When to use this

Someone's sent you a 40-slide finance deck. You have ten minutes before the meeting. You don't need every chart — you need the gist. What changed, what's good, what's bad, and what calls for a decision.

Use this when you want a fast, plain summary you can act on. Paste in the deck text or your notes, and get back one page. You stay in charge of the figures and the call.

## The prompt

```
You are helping an executive read a finance deck fast. I'll paste the deck's text and notes below. Turn it into a one-page read.

Structure it as:
1. Headline — two or three sentences. How did the period go overall? Lead with the single thing that matters most.
2. What changed — the key movements since last period, each with the number. Up, down, or flat. Keep it short.
3. What needs a decision — the one to three items that call for a choice or a follow-up. Say what the choice is.

Rules:
- Use only the numbers and facts I give you. Do not invent or estimate any figure.
- If a number looks important but is missing, list it under "Gaps" instead of guessing.
- Plain language. No jargon, no hype. Short sentences.
- Keep the whole thing to one page.

Deck text and notes:
[PASTE THE DECK TEXT OR YOUR NOTES — revenue, costs, margin, cash, variances, anything flagged. Rough is fine.]
```

## Before and after

**Before — the dense notes you'd paste in:**

> - Q3 rev $4.2M vs $3.8M Q2, plan was $4.5M <!-- noev: worked example -->
> - Gross margin 61%, down from 64% last Q, cloud costs up <!-- noev: worked example -->
> - Opex flat ~$2.1M <!-- noev: worked example -->
> - Cash $6.8M, burn $700K/mo, ~9 mo runway <!-- noev: worked example -->
> - One vendor contract renews next month, 18% price hike proposed <!-- noev: worked example -->
> - Sales hiring behind, 3 of 5 roles open

**After — the one-pager it produces:**

> **Headline.** Revenue grew to $4.2M but landed under the $4.5M plan. Margin slipped on rising cloud costs, and runway is tight at about nine months. <!-- noev: worked example -->
>
> **What changed**
> - Revenue up to $4.2M from $3.8M last quarter — short of the $4.5M plan. <!-- noev: worked example -->
> - Gross margin fell to 61% from 64%, driven by higher cloud costs. <!-- noev: worked example -->
> - Operating expenses held flat at about $2.1M. <!-- noev: worked example -->
> - Cash at $6.8M, burning $700K a month — roughly nine months of runway. <!-- noev: worked example -->
>
> **What needs a decision**
> - A vendor wants an 18% price increase at next month's renewal. Accept, negotiate, or switch. <!-- noev: worked example -->
> - Sales hiring is behind, with three of five roles open. Decide whether to push harder or hold. <!-- noev: worked example -->
>
> **Gaps**
> - No customer or retention numbers in the notes — add them if they drove the miss.

## Make it yours

- **Change the lens.** Add *"Read this as a cash question — lead with runway and burn."*
- **Match your format.** Paste last month's one-pager and add *"Use this same shape and order."*
- **Get the questions, not just the summary.** Add *"List the three sharpest questions I should ask in the meeting."* (See [Ask Better Questions of the Numbers](/ai-use-cases/executive-leadership/finance-performance/ask-better-questions-of-the-numbers.md).)
- **Tighten it more.** Add *"Cut it to five bullets I could read aloud in a minute."*

## Watch out for

- **Check every figure against the deck.** This is the one that bites. A summary can drop a number, round it wrong, or swap two of them — and the clean layout makes the error look trustworthy. Before you rely on a figure or repeat it, find it in the source deck and confirm it matches.
- **A confident summary can still distort.** The tool can frame a flat quarter as good news, or bury a real risk in a tidy bullet. Read the deck's flagged items yourself and make sure each one survived.
- **You own the decision, not the tool.** The one-pager tells you what changed. What to do about the price hike or the hiring gap is your call — and your finance team's input — not the summary's.
