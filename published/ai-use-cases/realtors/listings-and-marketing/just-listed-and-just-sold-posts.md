---
type: Playbook
title: "Just-Listed and Just-Sold Posts"
description: "Turn a new listing or a recent sale into platform-ready social posts."
tags: [listings-and-marketing, realtors]
timestamp: "2026-06-30"
---

## When to use this

You've got a new listing or a fresh closing and you need posts for three platforms — yesterday. The facts are in your head (or your CMA notes), but staring at a blank caption field burns time you don't have. Paste the prompt below, fill in your facts, and get platform-ready drafts back.

## The prompt

Paste this into ChatGPT, Claude, or Gemini. Fill in the brackets. Leave a field blank if it doesn't apply.

```text
You're helping me write social media posts for a real estate listing or recent sale.
Write one post per platform listed below.

Property facts:
- Status: [Just Listed / Just Sold]
- Type: [e.g. 3-bed 2-bath craftsman bungalow]
- City/neighborhood: [e.g. Oak Park, IL — Lincoln Square area]
- Price or sale price: [e.g. listed at $449,000 / sold at $462,000]
- Standout feature: [the one thing that sells it]
- Two or three other details: [e.g. updated kitchen, detached garage, walk to the train]

Platforms: [e.g. Instagram, Facebook, LinkedIn]
Tone: [e.g. warm and neighborhood-focused / upbeat / professional]

Rules:
- Write one post per platform. Respect each platform's character limit:
    Instagram: up to 2,200 characters; up to 5 relevant hashtags.
    X (Twitter): up to 280 characters (free accounts).
    LinkedIn: up to 3,000 characters.
    Facebook: keep it conversational and under 300 characters for feed visibility.
- Lead with the standout feature, not the bed/bath count.
- For Just Listed: close with a call to action (schedule a showing, link in bio, DM me).
- For Just Sold: close with a line for buyers or sellers who want the same result.
- Describe the PROPERTY and its features, never the kind of buyer who should live there.
- Do NOT use wording that signals a preference based on race, color, national origin,
  religion, sex, familial status, or disability.
- Do NOT invent facts I didn't give you — no school ratings, no neighborhood comparisons,
  no made-up walk scores.
- Use ONLY the facts I provided above.
```

## Before and after

**What you start with** — your raw notes after the showing:

> just listed - craftsman bungalow oak park - 3bd 2ba - $449k - updated kitchen w quartz + farmhouse sink 2023 - detached 2 car garage - walk to green line - hardwood floors throughout - great for young professionals or first-time buyers - need posts for insta, facebook, linkedin  <!-- noev: illustrative sample figure in a demo -->

**What you get back:**

> **Instagram**
> That kitchen will stop you mid-tour. ✨ Just listed in Oak Park: a 3-bed, 2-bath craftsman bungalow at $449,000 with a fully updated kitchen — quartz counters, farmhouse sink, all done in 2023. Hardwood floors run room to room, and the detached 2-car garage means you're never circling the block. The Green Line is a short walk. Link in bio for the full tour. DM me to schedule a showing.  <!-- noev: illustrative sample figure in a demo -->
> #OakParkRealEstate #JustListed #ChicagoHomes #CraftsmanHome #OakParkIL

> **Facebook**
> Just listed in Oak Park! This 3-bed craftsman bungalow has a stunning 2023 kitchen, hardwood floors, a 2-car garage, and an easy walk to the Green Line — all at $449,000. DM me or tap the link to schedule a showing.  <!-- noev: illustrative sample figure in a demo -->

> **LinkedIn**
> Excited to share a new listing in Oak Park, IL. This 3-bedroom, 2-bath craftsman bungalow is listed at $449,000 and checks a lot of boxes: a beautifully updated kitchen (quartz counters, farmhouse sink — completed 2023), hardwood floors throughout, a detached 2-car garage, and walkable access to the Green Line. If you or someone you know is exploring the Oak Park market, I'd love to connect. Reach out directly or schedule a showing through the link.  <!-- noev: illustrative sample figure in a demo -->

Two things changed: the kitchen leads instead of the bedroom count, and "great for young professionals or first-time buyers" is gone. That kind of language signals a buyer preference and is a fair-housing risk — the prompt's rule tells the AI to leave it out.

## Know the limits

**Platform character limits (as of mid-2026).** The prompt bakes these in, but they're worth knowing if a draft comes back too long:

- **Instagram**: up to 2,200 characters per caption (Instagram doesn't document the caption limit clearly, so treat that number as approximate). On hashtags, use up to **5**. Instagram is rolling its cap down from 30 to five ([Instagram, 2026](#ev-instagram-hashtag-limit-5-realtors)). A few relevant tags beat a wall of generic ones.
- **X (Twitter)**: **280 characters** for free accounts ([X, 2026](#ev-x-post-character-limit-280-realtors)). Premium subscribers get longer posts, but your audience is mostly on free accounts.
- **LinkedIn**: **3,000 characters** per post ([LinkedIn, 2026](#ev-linkedin-post-character-limit-3000-realtors)).
- **Facebook**: the technical limit is very high, but feeds truncate after a couple of lines. Keep posts short — roughly under 300 characters — so your key line shows without a "See more" tap. Check Facebook's current Help Center for specifics.

Limits can change. If a post gets flagged for length, check the platform's current help docs before tweaking by hand.

**Fair housing applies here too.** Your social posts reach the public, so the Fair Housing Act covers them the same way it covers your MLS description. Don't describe who should buy — describe the home. Avoid "perfect for families," "quiet professional community," "ideal for empty nesters," and similar phrases. Describe rooms, features, and what's nearby. The prompt includes this rule, but read every draft before it goes live.

**Accuracy is on you.** The AI uses only what you give it. If your notes are off — wrong price, wrong year on the update, a feature you're not sure about — those errors go straight into the post. Confirm the facts before you paste them in.

## Make it yours

- **Lock in your tone.** Change the tone line to match how you actually write — "neighborhood storyteller," "crisp and data-forward," "warm and conversational." Run it twice with different tones and pick the stronger opener.
- **Add an image caption.** Append "Also write a 10-word image caption for each platform" to get photo overlay text in the same pass.
- **Save it as a template.** Once the rules read right for you, keep the prompt in a note and swap the facts for each new listing.
- **Ask for variants.** Append "give me two versions of the Instagram post — one under 150 characters" to get a short option for Stories or carousel slides.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Instagram — *Use hashtags on Instagram — Instagram Help Center (cap reduced from 30 to 5 per Instagram's own announcement)*, 2026.** Instagram will gradually update the number of hashtags that you can include in a caption for a reel or post to five. [View source](https://help.instagram.com/351460621611097){#ev-instagram-hashtag-limit-5-realtors} · verified 2026-06-24 · ⚠ secondary mirror
- **X (formerly Twitter) — *Counting Characters — X Developer Platform*, 2026.** Posts on X can contain up to 280 characters. [View source](https://docs.x.com/fundamentals/counting-characters){#ev-x-post-character-limit-280-realtors} · verified 2026-06-24 · primary
- **LinkedIn — *Post and share updates — LinkedIn Help*, 2026.** The character limit for a post is 3000 characters. [View source](https://www.linkedin.com/help/linkedin/answer/a528176){#ev-linkedin-post-character-limit-3000-realtors} · verified 2026-06-24 · primary
