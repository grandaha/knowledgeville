---
type: Playbook
title: Measuring Adoption
description: "What to instrument and what good targets look like: depth of use over logins, early signals of a stall, and reporting up."
tags: [enablement, measurement, metrics]
timestamp: "2026-07-02"
---

You cannot manage adoption you cannot see, and the easiest thing to measure is the least useful. Logins tell you people opened the tool. They say nothing about whether the work changed. A useful measurement stack tracks depth of use, warns you early when a rollout is stalling, and gives your sponsor a number they trust.

## When to use this

Set this up before the first rollout, not after. Deciding what good looks like in advance is what lets you tell progress from noise later.

## What to instrument

Instrument three layers, not one:

- **Activity** — who is using AI, and how often. The floor, not the goal.
- **Depth** — which workflows AI is embedded in, and how far.
- **Outcome** — time saved, quality, or throughput in the targeted work.

Wire in what you can from the tools, but do not wait for perfect telemetry. A simple pulse survey asking whether this changed how you work beats a dashboard you never ship.

## Depth of use over logins

This is the distinction that matters most. A team where everyone logged in once and stopped looks identical to a thriving one, if you count only seats. Measure the depth instead:

- Repeat use in a specific workflow, not first use.
- Weekly and daily active use over time, not a one-off snapshot.
- Whether the work now routes through AI by default, or only when someone remembers.

Real adoption is habit. Habit shows up as sustained, repeated use in the same workflow. This is the same distinction the [AI Adoption Framework](/enterprise-ai-transformation/tracks/06-ai-adoption-and-culture/02-ai-adoption-framework.md) draws as access versus adoption.

## What good targets look like

Set targets against your own baseline, by workflow, not against a vendor's headline number. A healthy program shows occasional use turning into weekly use, and weekly into daily, in the workflows you chose. Set a floor you expect a supported team to clear. Treat a team well below it as a signal to investigate, not to scold.

## Leading signals of abandonment

Catching a stall early is the whole point of measuring. Watch for:

- Use that spikes at launch and then declines week over week.
- A widening gap between champions and everyone else.
- Rising logins with flat depth: people checking in, not working differently.

These show up weeks before a program is visibly dead. That is when intervention is cheap.

## Reporting up

Your sponsor is a distinct reader with a distinct need. They do not want your telemetry. They want to know whether the bet is paying off.

- Lead with outcome and depth, not activity.
- Show the trend and the next move, not a wall of charts.
- Be honest about stalls early. A surprise later costs you the sponsor.

## Watch out for

- **Vanity metrics.** Seats sold and logins are the easiest numbers and the least meaningful.
- **Snapshot thinking.** A single good week is not adoption. Trend it, or it did not happen.
- **Measuring to reassure.** Metrics chosen to look good instead of to tell the truth hide the stall you need to see.
- **Borrowed benchmarks.** Another company's targets are not yours. Measure against your own baseline.
