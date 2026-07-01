---
type: Playbook
title: Inbox Triage
description: "Have your assistant sort your unread mail into reply-now, read-later, and ignore, and surface what matters."
tags: [ai-playbooks, email]
timestamp: "2026-07-01"
---

This playbook has your assistant read your unread mail and sort it, so you open your inbox to a plan instead of a pile. It groups everything into three buckets and surfaces the few messages that actually need you. It drafts nothing and changes nothing.

## When to run it

Run this when your inbox feels heavy and you cannot tell what matters. Good at set times too — say mid-morning and after lunch. Run it any time you would otherwise skim your inbox and stall.

## What it needs

Read access to the user's email. That is all. You will read unread messages, sort them, and report back. You do not need permission to send, label, or file anything, because you will not do any of that.

## The playbook

1. Fetch the user's unread messages. If there are more than about 40, take the 40 most recent so the pass stays quick.
2. For each message, read the sender, subject, and enough of the body to judge it. Skim, do not study.
3. Sort each message into one of three buckets:
   - **Reply now** — it asks something of the user, or it is time-sensitive and needs a human answer.
   - **Read later** — worth reading, but no action today: newsletters worth keeping, long threads, updates.
   - **FYI / no action** — receipts, notifications, confirmations, automated noise.
4. Within **Reply now**, pick the two or three messages that genuinely matter most. Weigh who sent it, what they are asking, and how soon it is due.
5. Watch for anything urgent, sensitive, or unclear — a deadline today, a payment, a personal or legal matter. Set these aside to flag, do not guess at them.
6. Write a short summary: the three buckets with counts, then the top two or three messages named with one line each on why they matter. List anything you flagged in step 5 separately.
7. Present the summary to the user. Do nothing else — no replies, no labels, no filing. Stop here and wait.

## What it produces

A short, scannable readout: how your unread breaks down, the handful of messages that actually need you, and anything worth a second look. Nothing in your inbox changes.

```
Inbox triage — 34 unread

Reply now (5) · Read later (12) · FYI / no action (17)

Top messages:
- Priya Nair — "Re: Q3 budget sign-off" — asks for your
  approval before Thursday's finance review.
- Sam Okafor — "Contract redlines attached" — wants your
  reply on two clauses before they send to legal.
- Dana Lee — "Lunch next week?" — quick yes/no, no rush.

Worth a second look:
- "Invoice #4821 overdue" — payment-related, flagging so
  you can decide. I did not act on it.
```

## Guardrails

Read and organize only. Draft nothing, send nothing. Never reply, forward, delete, archive, label, file, or mark anything as read. You touch the inbox with read access and nothing more.

If a message looks urgent, sensitive, or ambiguous, do not act on it or guess. Flag it in your summary and let the user decide. This holds for anything about money, contracts, health, or personal matters.

When you are unsure which bucket fits, say so rather than forcing a guess. Respect private content — summarize what the user needs, do not quote sensitive detail they did not ask to see.

## Make it yours

- **Change the cadence.** Run it once each morning, or every few hours on a heavy day.
- **Adjust the buckets.** Add a "Waiting on me" or "From my manager" bucket if that matches how you work.
- **Widen or narrow the scope.** Triage one label or folder, or the last two days instead of only unread.
- **Tune what counts as urgent.** Tell the assistant which senders or topics always rise to the top.
