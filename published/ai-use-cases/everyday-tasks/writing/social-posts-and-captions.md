---
type: Playbook
title: Write Social Posts & Captions
description: Generate platform-ready posts and captions from one idea.
tags: [social-media, writing]
timestamp: "2026-06-24"
---

## When to use this

When you have something to share but can't find the right words, or you need the same idea formatted for multiple platforms at once. Works well for product announcements, event promos, behind-the-scenes moments, or just staying active when inspiration is thin.

## The prompt

```
You are a social media copywriter who writes in a natural, human voice — no hollow hype or cringe hashtag dumps.

Here's my idea: [describe what you want to share in 1–3 sentences]

My brand/personal voice is: [e.g. "friendly and direct", "dry and witty", "warm and encouraging"]

Please write posts for the following platforms:
- X: one punchy post, max 280 characters. No hashtags unless they genuinely add value.
- LinkedIn: a short update, max 3,000 characters. Professional but not stuffy. Start with a hook, not "I'm excited to announce."
- Instagram: a caption with a clear first line (the bit shown before "more"), then the rest of the caption. Add 3–5 relevant hashtags at the end.

Keep each platform's post feeling native to that platform — different length, different energy.
```

## Before and after

**Before** — the idea pasted into the prompt:

> We just shipped a small feature that lets users save their favourite templates. Took two weeks but our team is really proud of it. Voice: friendly and real.

**After** — excerpt of what the AI returns:

> **X:**
> We shipped something small today that I think you'll actually use — save your favourite templates. Two weeks of work. Worth it. 🎉
>
> **LinkedIn:**
> Two weeks ago, we set out to solve a small but annoying problem: having to rebuild the same template every time.
>
> Today we shipped it — you can now save your favourite templates and pull them up instantly.
>
> It's a small thing. But it's the kind of small thing that adds up.
>
> **Instagram:**
> Save the ones you love. ✨
>
> You can now save your favourite templates and reuse them whenever you need them — no rebuilding from scratch.
>
> This one took two weeks and a lot of iteration. We're really happy with how it turned out.
>
> \#productupdate #ux #buildinginpublic #saas #newfeature

## Know the limits

Platform limits matter — the AI won't always get them right on the first try, so check before you post.

- **X (Twitter):** Standard posts are capped at **280 characters** ([X Developer Docs, 2026](#ev-x-post-character-limit-280)). Keep it tight, or break a longer thought into a thread.
- **LinkedIn:** Posts can be up to **3,000 characters** ([LinkedIn Help, 2026](#ev-linkedin-post-character-limit-3000)). Anything longer needs to be published as an article instead.
- **Instagram hashtags:** You can use up to **5 hashtags** per post ([Instagram Help Center, 2026](#ev-instagram-hashtag-limit-5)). Instagram cut this from 30 to 5, saying fewer, well-chosen hashtags perform better — so the prompt asking for 3–5 is right where you want to be.
- **Caption length:** Instagram's caption character limit is not clearly documented in their Help Center. In practice, captions are cut off in the feed after the first 125 characters — make your first line count.

## Make it yours

- **One platform only:** Remove the other platforms from the prompt and ask for three variations with different tones instead.
- **Add your own examples:** Drop in a recent post that performed well and say "match this energy."
- **Thread format:** For X, ask for "a 5-post thread instead of a single post."
- **Scheduling copy:** Add "also write a short note I can use as the caption when I schedule this in a social tool."

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **X (formerly Twitter) — *Counting Characters — X Developer Platform*, 2026.** Posts on X can contain up to 280 characters. [View source](https://docs.x.com/fundamentals/counting-characters){#ev-x-post-character-limit-280} · verified 2026-06-24 · primary
- **LinkedIn — *Post and share updates — LinkedIn Help*, 2026.** The character limit for a post is 3000 characters. [View source](https://www.linkedin.com/help/linkedin/answer/a528176){#ev-linkedin-post-character-limit-3000} · verified 2026-06-24 · primary
- **Instagram — *Use hashtags on Instagram — Instagram Help Center (cap reduced from 30 to 5 per Instagram's own announcement)*, 2026.** Instagram will gradually update the number of hashtags that you can include in a caption for a reel or post to five. [View source](https://help.instagram.com/351460621611097){#ev-instagram-hashtag-limit-5} · verified 2026-06-24 · ⚠ secondary mirror
