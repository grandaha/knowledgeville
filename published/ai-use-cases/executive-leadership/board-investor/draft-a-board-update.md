---
type: Playbook
title: Draft a Board Update
description: "Turn the quarter's facts into a clear, honest board update."
tags: [board-investor, recipe]
timestamp: "2026-06-28"
---

## When to use this

You have the quarter's facts — the revenue number, the headcount you added, the deal that slipped, the launch that landed — and a board update due. The facts aren't the hard part. The hard part is shaping them into something a board can read in a few minutes and trust. That means being clear on what went well, honest about what didn't, and specific about what you need from them.

Use this when you have the raw material and want a strong first draft to edit, not a blank page to fill.

## The prompt

```
You are helping a CEO write a clear, honest update to their board of directors. Turn the facts below into a board update.

Structure it as:
1. TL;DR — three or four sentences a busy director can read first: how the quarter went overall, and the one or two things you most need them to know.
2. Highlights — what went well, with the numbers.
3. Lowlights / risks — what went wrong or is at risk, stated plainly. Do not soften or spin these.
4. Key metrics — a short table of the numbers I give you, this period vs. last.
5. Asks — specific things I need from the board (intros, a decision, advice).

Rules:
- Use only the facts I provide. Do not invent numbers, metrics, or context. If something important seems missing, list it under "Gaps to fill" at the end instead of guessing.
- Plain, direct language. No hype, no jargon, no filler.
- Honest tone — a board that trusts your bad news will trust your good news.

Facts for this quarter:
[PASTE YOUR RAW NOTES — revenue, growth, hires, departures, wins, misses, product, cash/runway, what you need. Bullet points are fine.]
```

## Before and after

**Before — raw notes you'd paste in:**
> - Revenue $1.2M this Q, was $950K last Q <!-- noev: worked example -->
> - Signed BigCo, our biggest deal ever
> - Lost two engineers, hiring is slow
> - Mobile launch slipped to next Q, my fault, underestimated it
> - Cash: ~14 months runway
> - Need 2 intros to potential VP Eng candidates

**After — the kind of update it produces:**

> **TL;DR.** Strong quarter on revenue — up 26% to $1.2M, led by our largest-ever deal (BigCo). The one thing to flag: our mobile launch slipped a quarter, and engineering hiring is behind. Runway is healthy at ~14 months. My main ask: intros to two VP Engineering candidates. <!-- noev: worked example -->
>
> **Highlights**
> - Revenue grew to $1.2M, up from $950K last quarter (+26%). <!-- noev: worked example -->
> - Closed BigCo — our largest contract to date.
>
> **Lowlights / risks**
> - The mobile launch slipped to next quarter. I underestimated the scope; that's on me.
> - We lost two engineers and hiring has been slow, which is what put mobile at risk.
>
> **Key metrics**
>
> | Metric | This quarter | Last quarter |
> |---|---|---|
> | Revenue | $1.2M | $950K | <!-- noev: worked example -->
> | Runway | ~14 months | — |
>
> **Asks**
> - Two intros to strong VP Engineering candidates.
>
> **Gaps to fill**
> - No prior-quarter runway given, so the trend isn't shown.
> - No customer or retention numbers included — add if the board tracks them.

## Make it yours

- **Set the length.** Add *"Keep it under one page"* or *"Give me a tight version and a detailed version."*
- **Match how your board reads.** *"My board prefers a narrative to a metrics table — write the metrics into prose."*
- **Pre-empt the hard questions.** Add *"After the update, list the three toughest questions a director might ask, so I can prepare."* (See [Prep Board / Investor Q&A](/ai-use-cases/executive-leadership/board-investor/prep-board-investor-qa.md).)
- **Reuse your format.** Paste last quarter's update and add *"Match this structure and tone."*

## Watch out for

- **Check every number against the source.** A board update is the wrong place for a transcription slip. The prompt is told not to invent figures, but it can still copy one wrong — verify each against your actual numbers before you send.
- **You decide what to disclose, not the tool.** What goes to a board — and how a risk is framed — is your judgment and sometimes your counsel's. Treat the draft as a starting point, not a disclosure decision.
- **Don't let it smooth over bad news.** AI tends to soften. Read the lowlights and make sure the slip, the miss, or the risk still reads as plainly as it should. That honesty is what earns a board's trust.
