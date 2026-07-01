---
type: Playbook
title: Follow-up Tracker
description: "Have your assistant scan your mail for open loops and tell you who owes whom."
tags: [ai-playbooks, email]
timestamp: "2026-07-01"
---

This playbook is a weekly scan of your recent mail that surfaces open loops. It reads what came in and what you sent. Then it tells you who is waiting on a reply, and what you are still waiting to hear back on. Good for when you suspect a few things have slipped but cannot say which.

## When to run it

Run it weekly, on the same day each week. Or run it any time you feel like threads are getting missed and you want a clean picture.

## What it needs

Read access to the user's mailbox — sent and received. That is enough. The assistant reads and drafts only; it never sends, replies, or changes a thing.

## The playbook

1. Set the window. Default to the last 14 days unless the user names a different range.
2. Read the user's received mail from that window. For each thread, note the sender, the topic, and the date of the latest message. Note whether it asks the user a question or waits on them for something.
3. Read the user's sent mail from that window. Note who each message went to, the topic, the date, and whether the user asked for something or posed a question.
4. Match messages into threads so a back-and-forth reads as one loop, not many.
5. Build the "You owe a reply" list. Include any thread where the latest message is from someone else, it wants a response, and the user has not replied since.
6. Build the "Waiting on others" list. Include any thread where the user's message was last, it asked for something, and no reply has come back.
7. Drop the noise. Skip newsletters, automated notifications, receipts, and calendar invites. Skip threads that read as closed ("thanks!", "sounds good", "will do").
8. For each item, work out roughly how long it has been sitting. Count days from the last message to today, and round to a plain phrase like "3 days" or "2 weeks".
9. Sort each list oldest-first, so the most stale loops sit at the top.
10. Flag anything ambiguous rather than guessing — a thread you cannot tell is open or closed goes in a short "Not sure" note under the lists.
11. Present both lists to the user in the chat. Take no other action.

## What it produces

Two short lists, oldest loop first, each line naming the person, the topic, and how long it has been sitting. A "Not sure" note follows if any thread was hard to read. Nothing is sent; nothing is changed.

```
Follow-up scan — last 14 days

You owe a reply (3)
  • Priya R. — budget sign-off she asked for — 9 days
  • Marcus T. — feedback on the draft deck — 4 days
  • Jordan L. — intro to the design vendor — 2 days

Waiting on others (2)
  • Sam K. — you asked for the Q3 numbers — 11 days
  • Dana W. — you sent the signed contract, no confirmation — 6 days

Not sure (1)
  • Alex P. — "let's circle back" thread — can't tell if it's your move
```

## Guardrails

The assistant reads and drafts only. It never sends, replies, nudges, forwards, deletes, or marks anything — on any thread, for any reason. Its job is to report open loops, not to chase them.

It reports; you decide. No message goes out without you writing and sending it yourself.

When a thread is ambiguous — unclear whose move it is, or whether it is even open — the assistant flags it in the "Not sure" note. It does not guess and it does not pad the lists to look thorough.

Treat mail as private. Keep topics short and factual, do not quote sensitive contents back, and never act on what you read beyond building these lists.

## Make it yours

- Change the window. Ask for the last 7 days for a tighter view, or 30 for a full sweep after time away.
- Scope it to people. Ask for only your team, your manager, or one client, and the assistant filters to them.
- Set a staleness floor. Ask it to hide anything under 3 days so only the truly stale loops show.
- Add a priority flag. Ask it to mark loops with a named person or a keyword ("contract", "invoice") so they jump out.
