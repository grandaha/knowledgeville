---
type: Playbook
title: Summarize a Document
description: Get the key points of a long document in seconds.
tags: [summarizing, documents]
timestamp: "2026-06-24"
---

## When to use this

You have a long document — a report, contract, article, or meeting brief — and you need the gist before a call or decision. Paste it in and skip the 45-minute read.

## The prompt

```
You are a sharp executive assistant. I'm going to paste a document below. Please summarize it for me.

Return:
- A 2–3 sentence overview of what this document is about
- 5 key points, each in one sentence
- Any decisions, deadlines, or action items buried in the text (list them separately, or say "none found")

Keep the language plain and direct. Do not add commentary or opinions — just extract what's there.

Here is the document:

[PASTE YOUR DOCUMENT HERE]
```

## Before and after

**Before:** A 12-page vendor proposal about a new software platform, full of marketing language, feature tables, and pricing appendices. You have 10 minutes before the vendor call.

**After:**

> **Overview:** This is a proposal from Apex Systems for a workflow automation platform aimed at mid-size operations teams. The proposal covers three pricing tiers and a 90-day implementation timeline.
>
> **Key points:**
> 1. Base tier starts at $1,200/month for up to 50 users. <!-- noev: worked example -->
> 2. Full API access requires the Enterprise tier.
> 3. A dedicated onboarding manager is included in all tiers.
> 4. Data migration support is limited to structured formats (CSV, Excel).
> 5. Contract is annual with a 30-day cancellation window after year one.
>
> **Decisions / deadlines:** Proposal expires July 15. Pilot program slots are limited to 3 new clients this quarter.

## Make it yours

- **Shorter:** Add "Give me a 3-bullet TL;DR — no more." to the top of the prompt.
- **Specific angle:** Replace the key points instruction with "Focus only on the financial terms and commitments."
- **Multiple documents:** Paste two documents separated by a divider and ask it to compare them on specific dimensions.
- **Jargon-heavy text:** Add "Define any technical terms the first time you use them."

## Watch out for

AI can miss nuance buried in footnotes or tables — always check the actual document for anything you'll sign or commit to. If the document is very long (over 20 pages), paste it in sections and ask for a rolling summary.
