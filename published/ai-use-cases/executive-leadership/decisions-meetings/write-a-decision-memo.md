---
type: Playbook
title: Write a Decision Memo
description: Turn a pending call into a crisp decision memo others can act on.
tags: [decisions-meetings, recipe]
timestamp: "2026-06-28"
---

## When to use this

You have a call to make. You've turned it over in your head, talked to a few people, and you're close to a decision. But it lives in your notes and your inbox, not on a page anyone else can follow.

A decision memo fixes that. It states the call, the reasoning behind it, and what happens next — in one page others can act on. Use this when you've done the thinking and want a clean draft to sharpen. The decision is yours; the tool just drafts it.

## The prompt

```
You are helping an executive write a clear decision memo. Turn the decision and context below into a structured memo.

Structure it as:
1. The decision — one or two sentences. State the call plainly, up front.
2. Why — the reasoning behind it, in three or four points.
3. Options considered — the main alternatives, each with a one-line "why not."
4. Risks and what would change my mind — the real downsides, and the signals that would make me reconsider.
5. What happens next — the concrete steps, who owns each, and by when.

Rules:
- Use only what I give you. Do not invent facts, numbers, owners, or dates. If something important is missing, list it under "Open questions" instead of guessing.
- Plain, direct language. Lead with the decision, not the background.
- Keep it to one page. A reader should grasp the call in the first three lines.

The decision and context:
[PASTE THE PENDING CALL + WHAT YOU KNOW — the question, the options, what you've heard, constraints, deadline, who's affected. Bullets are fine.]
```

## Before and after

**Before — the scattered version in your head:**
> We probably can't keep building both the API and the dashboard with this team. Sarah thinks API, Marco wants dashboard. Two big customers asked for the API. Dashboard demos better in sales. We're stretched thin. Need to decide before planning next week.

**After — the kind of memo it produces:**

> **The decision.** We'll focus the team on the API for the next quarter and pause new dashboard work.
>
> **Why**
> - Two of our largest customers have asked for the API directly. The dashboard demand is softer.
> - The team can't ship both well right now, and splitting it has slowed both.
> - The API unblocks integrations that the dashboard later depends on anyway.
>
> **Options considered**
> - *Keep building both.* Why not: it's what we're doing, and neither is shipping.
> - *Focus on the dashboard.* Why not: it demos well but lacks the committed customer pull the API has.
>
> **Risks and what would change my mind**
> - Sales may lose dashboard momentum. I'd reconsider if two or more deals stall on it this quarter.
> - If a third customer drops the API ask, the case weakens.
>
> **What happens next**
> - Sarah leads API delivery; she'll bring a scope and timeline to next week's planning.
> - Marco documents the dashboard state so we can restart cleanly later.
>
> **Open questions**
> - No deadline was given for the customer API commitments — confirm before we lock scope.

## Make it yours

- **Set the audience.** Add *"This goes to my exec team"* or *"This is for the board"* — the framing and detail shift.
- **Stress-test it first.** Add *"Before the memo, argue the strongest case against my decision."* If the case holds up, the memo is better for it.
- **Match how your team writes.** Paste an old memo and add *"Use this structure and tone."*
- **Trim or expand.** *"Make this half as long"* for a quick call, or *"add a one-paragraph summary at the top"* for a heavier one.

## Watch out for

- **The format is not the decision.** A clean memo can make a half-baked call look finished. The structure is the tool's job; the judgment is yours. A tidy layout is not evidence that the reasoning is sound.
- **Check that the recommendation is what you actually believe.** AI will write a confident case for whatever you feed it — including the wrong call. Read the "why" and the chosen option, and make sure they match your real view, not just the cleanest-sounding one.
- **Own the reasoning, not just the words.** You'll defend this memo in the room. If a point in it isn't one you'd stand behind out loud, cut it or rewrite it before you send.
- **Mind the gaps it papers over.** If the tool guessed an owner, a date, or a fact you didn't give it, catch it. Move anything uncertain to "Open questions" rather than letting a placeholder read as settled.
