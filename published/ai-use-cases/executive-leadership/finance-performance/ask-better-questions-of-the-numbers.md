---
type: Playbook
title: Ask Better Questions of the Numbers
description: Get a sharper set of questions to put to a finance report before a review.
tags: [finance-performance, recipe]
timestamp: "2026-06-28"
---

## When to use this

You've got a finance report in front of you and a review coming up. The numbers are there. What's missing is the right set of questions to put to them. Without them, you react to the charts in the meeting instead of testing what's behind them.

Use this when you want a sharper line of questioning before the meeting. The model reads your figures and hands back the pointed questions worth asking. It doesn't answer them. You decide which ones to raise, and what the answers mean.

## The prompt

```
You are helping an executive prepare for a finance review. I'll paste a report or a set of figures below. Your job is to give me a sharp list of questions to ask about it — not answers, not your own analysis of the numbers.

Return:
1. The questions I should put to whoever owns this report, grouped by theme (e.g. revenue, costs, cash, assumptions).
2. For each question, one line on why it's worth asking — what it would surface.
3. A short list of anything that looks missing or that I'd need before I could read this confidently.

Rules:
- Ask questions. Do not state conclusions about the numbers or compute new figures.
- Do not restate my figures back as if they're verified facts. If you reference one, mark it as "you reported X" so it's clear it came from me.
- Plain language. No jargon. Each question should be one a smart non-finance person could ask out loud.

Here's the report:
[PASTE THE REPORT OR FIGURES — tables, a summary, raw notes. Whatever you have.]

The review is about: [WHAT THIS MEETING IS FOR — e.g. quarterly close, a spend approval, a board prep].
What I most want to understand: [THE ONE OR TWO THINGS ON YOUR MIND].
```

## Before and after

**Before — the figures you'd paste in:**
> Q3 revenue $4.2M, up from $3.8M in Q2. Gross margin 61%, was 64% last Q. Sales headcount up 30%. Cash burn $600K/mo, runway 11 months. New enterprise tier launched mid-Q. <!-- noev: worked example -->

**After — the kind of questions it gives back:**

> **Revenue**
> - You reported revenue up to $4.2M. How much of that growth came from the new enterprise tier versus the existing base? It tells you if the new bet is working or just masking flat core sales. <!-- noev: worked example -->
> - Is any of the $4.2M one-time or pulled forward from Q4? It separates a real trend from a good-looking quarter. <!-- noev: worked example -->
>
> **Margin and costs**
> - Margin dropped from 64% to 61%. What drove it — the new tier's cost to serve, or something else? It tells you whether the dip is a choice or a leak. <!-- noev: worked example -->
> - Sales headcount is up 30%. Is revenue per rep holding, or did we add people faster than they're producing? It surfaces whether the hiring is paying off yet. <!-- noev: worked example -->
>
> **Cash**
> - At $600K/month burn, what's the single biggest assumption behind the 11-month runway figure? It shows you how fragile the timeline is. <!-- noev: worked example -->
>
> **Looks missing**
> - No customer count or churn, so you can't tell if revenue grew from more customers or higher prices.
> - No prior-year comparison — only quarter-over-quarter. Seasonality could be hiding here.

## Make it yours

- **Aim it at one decision.** Add *"Only give me questions that matter for approving next quarter's spend."*
- **Set the depth.** *"Give me the five sharpest questions, not twenty"* — or ask for an exhaustive list if you're going deep.
- **Stress-test the rosy read.** Add *"Assume this report is putting its best foot forward. What would a skeptical board member ask?"*
- **Prep the follow-up.** *"For each question, give me a likely answer and the follow-up I'd ask if it's evasive."*

## Watch out for

- **The model probes; you verify.** Its job is to ask good questions, not to vouch for your figures. Don't let it restate or recompute a number — it can copy one wrong or quietly do bad math. Every figure you carry into the room gets checked against the source first.
- **A confident question isn't a confirmed problem.** A sharp question can imply the number is wrong when it's fine. The question is a prompt to look — the answer comes from the report and the people who own it, not the model.
- **You own which questions to ask.** A list of twenty questions isn't a plan. Pick the few that fit the room and the decision. Reading the answers is your call, not the tool's.
