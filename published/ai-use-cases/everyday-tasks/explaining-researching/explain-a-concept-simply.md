---
type: Playbook
title: Explain a Concept Simply
description: Get a plain-language explanation of anything, at your level.
tags: [explaining, learning]
timestamp: "2026-06-24"
---

## When to use this

You've encountered a term, idea, or topic that you don't fully understand. You want a clear explanation, without wading through jargon or hours on Wikipedia.

## The prompt

```
You are a patient teacher who specializes in plain-language explanations.

I want to understand: [CONCEPT OR TOPIC]

My background: [e.g. "I'm not technical", "I know a bit about finance but nothing about investing", "I'm a high-school student"]

Please explain it to me as if I'm smart but completely new to this subject. Use an analogy if it helps. Keep it under 200 words, then ask me if I'd like to go deeper on any part.
```

## Before and after

**Before:** The reader hits the phrase "asymmetric encryption" in an article and has no idea what it means.

**After (excerpt):**

> Think of asymmetric encryption like a padlock that anyone can snap shut, but only you have the key to open. When you visit a secure website, the site hands you an open padlock (the public key). You snap it shut on your data, and it travels to the site. Only the site — holding the matching key — can open it.
>
> Want me to go deeper on how the keys are generated, or how this protects your passwords?

## Make it yours

- Add `"Use a real-world example from [cooking / sports / everyday shopping]"` if generic analogies don't land for you.
- Change the word count: `"Keep it under 100 words"` for a one-liner, or drop the limit for a fuller treatment.
- Ask for a comparison: `"Also tell me how it's different from [related concept]"`.
- If you're helping a child understand something, replace the background line with `"Explain it to an 8-year-old"`.

## Watch out for

AI explanations can be confidently wrong on technical details. For anything high-stakes — medical, legal, financial — treat the explanation as a starting point and verify with a credible source. It's great for building intuition, less great as a final reference.
