---
type: Playbook
title: Extract Key Details from Text
description: Pull specific fields out of unstructured text.
tags: [data, extraction]
timestamp: "2026-06-24"
---

## When to use this

You have a block of text — an email, a contract clause, a product description, a support ticket — and you need specific fields pulled out of it without reading the whole thing yourself. Useful when you have one piece of text or a handful of them and need the same fields from each.

## The prompt

```
You are a detail extractor. I will give you a block of text and a list of fields I need. Your job is to pull exactly those fields from the text and return them as a simple list.

Fields I need:
[LIST YOUR FIELDS HERE — one per line, e.g. "Sender name", "Deadline", "Requested amount", "Next step"]

Rules:
- Use only what is explicitly stated in the text. Do not guess or fill in gaps.
- If a field is not present, write "Not mentioned" next to it.
- Keep each answer short — a phrase or a date, not a full sentence.
- Do not summarize or rephrase anything else.

Text to extract from:
[PASTE YOUR TEXT HERE]
```

## Before and after

**Before** — an email excerpt:

> Hi team, just a reminder that the invoice from Apex Supplies ($4,200) needs to be approved by the end of day Friday. Please route to Marcus in finance. Let me know if you have questions — Jamie <!-- noev: worked example -->

Fields requested: Vendor name · Amount · Deadline · Approver · Sender

**After** — what the AI returns:

- **Vendor name:** Apex Supplies
- **Amount:** $4,200 <!-- noev: worked example -->
- **Deadline:** End of day Friday
- **Approver:** Marcus (finance)
- **Sender:** Jamie
- **Not mentioned:** (all fields found)

## Make it yours

- Add "format the output as a markdown table" if you're extracting from multiple texts and want to compare them side by side.
- Specify a format for certain fields: "Return dates as YYYY-MM-DD."
- If extracting from contracts or legal text, add: "quote the exact sentence the answer comes from."
- Paste several texts in numbered blocks and ask it to produce one row per text.

## Watch out for

When a field appears multiple times with different values — say, two deadlines mentioned in one email — the AI may pick one and silently drop the other. If precision matters, ask it to "list all occurrences" for fields that might repeat. Also, it will not catch information that's implied rather than stated; if the deadline is "before the weekend" in an email sent Thursday, it won't infer Friday.
