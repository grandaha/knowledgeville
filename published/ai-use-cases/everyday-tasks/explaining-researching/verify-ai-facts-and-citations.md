---
type: Playbook
title: "Verify AI's Facts and Citations"
description: Catch fabricated citations and wrong facts before you rely on what AI told you.
tags: [explaining-researching, verification]
timestamp: "2026-07-05"
---

## When to use this

AI gave you a specific fact, statistic, quote, or source. You're about to actually use it — in a document, a decision, or something you'll repeat to someone else. Not needed for pure brainstorming or a first-pass explanation you already know you'll double-check later.

## The prompt

```
Before I use anything you just told me, help me verify it.

For each specific fact, statistic, or claim in your last answer, tell me separately:
1. The exact claim.
2. Whether you have a specific, real source for it (name it, and link it if you can) — or whether this is your own synthesis or inference rather than something a source directly states.
3. Your honest confidence: well-established, actively debated, or something you're not fully sure about.

If you don't have a real primary source for something, say so plainly instead of presenting it with the same confidence as something you do.
```

This surfaces what the AI is willing to flag as shaky — it doesn't reliably catch its own confident fabrications. A claim labeled "well-established" or "sourced" still needs the source opened, not less checking.

## Before and after

**Before:** You ask an AI tool for the typical price range for a service you're about to quote a client. It gives you a confident-sounding number with no source attached.

**After (excerpt):**

> Claim: "typical range is $8,000-$15,000." <!-- noev: hypothetical worked example, explicitly labeled unsourced in the next line -->
> Source: no specific report backs this figure — it's my own synthesis from general patterns, not a cited statistic.
> Confidence: moderate at best. Treat this as a rough starting point, not something to quote as fact.

Now you know to check the number independently before it goes in front of a client. You won't repeat an estimate as if it were sourced.

## Make it yours

- If the answer is long, ask it to list only the claims it's **least** confident about — that's where your verification time is best spent.
- If the AI names a source, actually open it. Don't count a plausible-sounding title as verified — open the link and check it actually says what the AI claimed. This is the one step that touches real ground truth; the rest of this page is just routing your attention toward it faster.
- Some tools now do part of this for you. Gemini's "Double-check response" feature cross-references its own answer against Google Search results. It highlights where they agree or disagree, so you can see at a glance which parts to trust more.

## Watch out for

Grounding an AI's answer in real search or retrieval helps a lot, but it changes the odds. It doesn't eliminate the problem. One independent study looked at deep-research tools built specifically for citation-backed research. Even those tools still generate a real share of hallucinated citations: "We find that 3-13% of citation URLs are hallucinated. They have no record in the Wayback Machine and likely never existed" ([Rao, Wong & Callison-Burch, 2026](#ev-upenn-2026-deep-research-citation-hallucination-rates)).

Grounding is also only as good as what it's grounded on. A Stanford study of AI legal-research tools found retrieval-based tools cut hallucination sharply compared to general-purpose models. Even so, one tool "hallucinated more than 34% of the time" ([Stanford RegLab/HAI, 2024](#ev-stanford-reglab-2024-legal-ai-hallucination-rates)). Researchers stopped short of calling any tool tested "hallucination-free." Treat "the AI searched for this" as meaningfully better than "the AI just generated this from memory" — never as a guarantee.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Rao, Wong, Callison-Burch (University of Pennsylvania) — *Detecting and Correcting Reference Hallucinations in Commercial LLMs and Deep Research Agents*, 2026.** We find that 3-13% of citation URLs are hallucinated. They have no record in the Wayback Machine and likely never existed. [View source](https://arxiv.org/abs/2604.03173){#ev-upenn-2026-deep-research-citation-hallucination-rates} · verified 2026-07-05 · primary
- **Stanford RegLab / Stanford HAI — *AI on Trial: Legal Models Hallucinate in 1 out of 6 (or More) Benchmarking Queries*, 2024.** the Lexis+ AI and Ask Practical Law AI systems produced incorrect information more than 17% of the time. Westlaw's AI-Assisted Research hallucinated more than 34% of the time. They hallucinated between 58% and 82% of the time on legal queries. [View source](https://hai.stanford.edu/news/ai-trial-legal-models-hallucinate-1-out-6-or-more-benchmarking-queries){#ev-stanford-reglab-2024-legal-ai-hallucination-rates} · verified 2026-07-05 · primary
