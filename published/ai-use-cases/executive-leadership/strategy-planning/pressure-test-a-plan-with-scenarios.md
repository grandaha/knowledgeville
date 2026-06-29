---
type: Playbook
title: Pressure-Test a Plan with Scenarios
description: "Stress a plan against best-, base-, and worst-case scenarios before you commit."
tags: [strategy-planning, workflow]
timestamp: "2026-06-28"
---

## When to use this

You've got a plan you like. The team's behind it. You're close to committing real money and time. That's the moment to stress it.

Use this before you sign off on a bet. A new market, a big hire, a product line, a price change. Anything where being wrong is expensive.

This isn't one prompt. It's a loop. You make the AI argue against you, turn after turn. It builds the scenarios, pokes the soft spots, and tries to break your plan. You hold the line on what matters and decide what to fix.

## A prompt to start

Open the loop like this. Then keep going.

```
You're a sharp, skeptical strategist. I'm about to commit to a plan, and I
want you to stress-test it before I do. Be a real devil's advocate. Don't
flatter it.

Here's the plan:
[DESCRIBE THE PLAN — the bet, the timeline, the resources]

Here's what I'm assuming is true:
[LIST YOUR KEY ASSUMPTIONS — demand, cost, timing, who does what]

First, build three scenarios for how this plays out: best case, base case,
worst case. Be concrete about what's different in each. Then wait.

After that, I'll ask you to dig into specific parts. Keep pushing. When I
give you a soft answer, say so.
```

## Work through it step by step

1. **Build the three scenarios.** Read all three before you react. The best case is easy; the worst case is where you learn something, so don't skim past it.
2. **Probe your assumptions.** Pick the assumptions the plan rests on. Ask the AI to challenge each one. "What if demand is half what I think?" Make it argue the other side hard.
3. **Find what breaks the plan.** Ask straight out: what single thing, if it went wrong, sinks this? There's usually one or two — finding them is the point of the exercise.
4. **Pressure the worst case.** Don't let it stay vague. Ask how you'd see it coming. Ask what the early warning sign would be. Ask what you'd do the day it happens.
5. **Decide what to harden.** Now you choose. Some risks you accept and move on. Some you fix before you commit. Some you set a tripwire for. Write down which is which.
6. **Run it past someone real.** The AI found the questions. A trusted colleague tells you if the fix holds. Close the loop with a human before you sign.

## What stays your call

The bet is yours. So is the line between a risk worth taking and one that isn't.

The AI is great at building scenarios and pushing on weak spots. It has no stake in the outcome. It doesn't know your appetite for risk, your timing, or what your gut is telling you.

Use it to surface what could go wrong. Then you decide what you can live with. Never let a tidy scenario talk you out of a bet you believe in, or into one you don't.

## Watch out for

- **A confident scenario isn't a forecast.** The AI will lay out a clean best, base, and worst case. They're prompts for your thinking, not predictions. The real worst case might be one it never named.
- **Don't let it round off the messy parts.** It tends to make plans look neater than they are. The friction, the politics, the thing nobody wants to say out loud — those are often what breaks a plan. Add them back.
- **Keep deal specifics out of a tool you don't control.** Named people, unannounced moves, anything sensitive — stress-test those in general terms, or offline.
- **Don't over-fix.** You can't harden against everything. If you try, you'll never commit. Pick the few risks that matter and let the rest go.
