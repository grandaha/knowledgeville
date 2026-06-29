---
type: Playbook
title: Scan a Market or Competitor Fast
description: Turn raw notes and links into a quick read on a market or competitor.
tags: [strategy-planning, recipe]
timestamp: "2026-06-28"
---

## When to use this

You've been gathering scraps about a market or a rival. A few links, some notes from a call, a screenshot of their pricing page. It's a pile, not a picture. You need a fast first read before a meeting, a board prep, or a gut check on a new bet.

Use this when you want that pile turned into a clean, structured scan you can react to. The tool does the sorting. You bring the judgment — what's reliable, and what it all means.

## The prompt

```
You are helping an executive get a fast first read on a market or competitor. Turn the raw material below into a structured scan.

Structure it as:
1. Snapshot — three or four sentences. What is this market or company, and why does it matter to me right now?
2. What stands out — the three or four most notable points from the material I gave you.
3. Strengths and weaknesses — a short two-column read, based only on what's in the notes.
4. Open questions — what I'd need to find out before I could act on this.
5. Confidence flags — mark any claim you're unsure about, or that looks like it might be out of date.

Rules:
- Use mainly the material I provide. If you add general context from your own knowledge, label it clearly as "[general context — verify]" so I know to check it.
- Do not invent numbers, dates, market sizes, or funding figures. If a key fact is missing, say so under "Open questions" instead of guessing.
- Flag anything that may have changed since your training — pricing, headcount, leadership, funding.
- Plain, direct language. No hype.

Material:
[PASTE YOUR RAW NOTES AND LINKS — call notes, pricing, product pages, articles, your own observations. Mark anything you already know is dated.]
```

## Before and after

**Before — the pile you'd paste in:**

> - Competitor: Northwind, sells scheduling software to clinics <!-- noev: worked example -->
> - Their pricing page: $49/user/month, was $39 last I checked <!-- noev: worked example -->
> - Heard on a call they just raised a Series B, maybe $30M? not sure <!-- noev: worked example -->
> - Customers love the calendar, complain support is slow
> - We're cheaper but our onboarding is clunky
> - Article said the clinic-software market is "growing fast"

**After — the kind of scan it produces:**

> **Snapshot.** Northwind is a scheduling tool for clinics, positioned a tier above us on price. It matters now because they appear to have fresh funding and are pushing upmarket, into our space. The read below is based on your notes; several figures need verifying before you act. <!-- noev: worked example -->
>
> **What stands out**
> - Priced at $49/user/month — above us, and reportedly up from $39, which may signal confidence or pressure. <!-- noev: worked example -->
> - A possible Series B (~$30M, unconfirmed) would give them runway to outspend us on growth. <!-- noev: worked example -->
> - Their calendar is a loved feature; their support is a known weak spot.
>
> **Strengths and weaknesses**
>
> | Strengths | Weaknesses |
> |---|---|
> | Strong core calendar | Slow support |
> | Apparent new funding | Higher price than you |
>
> **Open questions**
> - Is the ~$30M Series B real, and when did it close? <!-- noev: worked example -->
> - Is $49 the live price, or a plan tier? Confirm on their site. <!-- noev: worked example -->
> - How big is the clinic-scheduling market, really? "Growing fast" isn't a number.
>
> **Confidence flags**
> - Funding amount and round: unconfirmed, from a call.
> - Pricing: may be out of date — verify directly. <!-- noev: worked example -->

## Make it yours

- **Frame it against you.** Add *"Compare each point to my company, whose pitch is [PASTE]."*
- **Aim it at a decision.** Add *"I'm deciding whether to enter this market — sharpen the scan toward that call."*
- **Ask for the bear case.** Add *"End with the strongest reason this competitor beats us."*
- **Set the depth.** *"Keep it to half a page"* for a gut check, or *"go deep on their pricing"* when that's the crux.
- **Hand it a transcript.** Paste a raw call or interview and add *"Pull the market signals out of this."*

## Watch out for

- **Treat every fact as unverified until you check it.** The model may not have current data, and it can state stale or made-up facts with total confidence. A funding round, a price, a headcount, a market size — any of it can be wrong. Verify anything that drives a decision against the live source.
- **A scan is a starting point, not the verdict.** The structure makes a messy pile readable. It does not make the underlying facts true. The strategic conclusion is yours to draw.
- **Watch for confident filler.** If you gave it thin material, it may pad with plausible-sounding generalities. Push back: *"Only use what I gave you."* Then judge what's actually solid.
