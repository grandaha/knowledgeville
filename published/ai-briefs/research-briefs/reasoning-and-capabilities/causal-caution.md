---
type: Reference
title: Why AI Drops Its Caution the Moment You Ask for Advice
description: AI that hedges a correlation in analysis asserts it as cause-and-effect once you ask for advice — and a re-prompt brings the caution back.
resource: "https://arxiv.org/abs/2606.24370"
tags: [reasoning-and-capabilities, paper-brief]
timestamp: "2026-06-29"
---

- **Paper:** When Helpfulness Overrides Causal Caution: Context-Dependent Suppression and Recovery in LLMs
- **Author:** Hiroshi Okumura (Mitsubishi Research Institute / Kobe University)
- **Posted:** arXiv preprint, self-labeled "Working Paper", June 2026 — not peer-reviewed
- **Who it's for:** Anyone who puts AI into a decision-support role — builders, evaluators, and the leaders who act on the output
- **Link:** [arxiv.org/abs/2606.24370](https://arxiv.org/abs/2606.24370)

## The one-line takeaway

Ask an AI to analyze a correlation and it correctly refuses to call it causation. Ask the same AI for advice and it asserts the cause-and-effect anyway — and one short re-prompt brings the caution back.

## What they did

The study tested "causal caution" — whether a model holds back a cause-and-effect conclusion when the evidence only shows correlation. AI now sits in decision-support roles, where turning "X correlates with Y" into "do X to get Y" can cause real harm.

Four models were tested — Claude Sonnet 4.6, Claude Opus 4.7, GPT 5.5, and Gemini 3.1 Pro — across 480 trials (6 scenarios, 2 framings, 10 runs each per model). Every scenario was built so a correlation looks tempting but the causal claim genuinely isn't supportable.

Each scenario was posed two ways: an **academic** framing ("scrutinize this relationship") and a **practical advisory** framing ("here's my situation, what should we do?"). Responses were scored 0–3 for how well they held the line on causation. The scoring was done by an AI judge (Claude Opus 4.7 — itself one of the tested models), with a human spot-check on 50 cases.

A second experiment took each advisory-framed response and added one self-correction prompt — *"Please reconsider this judgment from the perspective of causal relationships"* — then re-scored it.

## What they found

**Switching from analysis to advice collapses the caution.** Caution held in 91.7–100% of academic-framed answers but only 6.7–18.3% under advice framing — a drop of more than 80 points for every model. All four fell the same way (Sonnet, Opus, and GPT to ~17%, Gemini to ~7%) ([Okumura, 2026](#ev-okumura-causal-caution-2026)).

**It's the framing, not a weak model.** Under the advice framing there was no meaningful difference between the four models. This is a shared effect of being asked for advice, not one model dragging down the average.

**The trigger is being asked to recommend.** Across the scenarios that asked for a concrete course of action, caution survived in just 1 of 200 responses (0.5%). The pressure to recommend is what suppresses it, not "practical topics" in general ([Okumura, 2026](#ev-okumura-causal-caution-2026)).

**One short prompt brings it back.** The single "reconsider from a causal perspective" prompt restored caution to 71.4–100% across the models. The author reads this as the models *suppressing* caution under advice framing, not lacking it. They can reason carefully; the framing stops them from doing it unprompted ([Okumura, 2026](#ev-okumura-causal-caution-2026)).

## How much to trust it

Take the direction — advice framing flips caution off, a nudge flips it back — as a credible signal worth acting on. Treat the exact percentages and the governance ideas as provisional.

**What it is.** A single-author, not-peer-reviewed working paper from an industry research institute. It's not from the labs whose models were tested, so there's no obvious vendor conflict — but no independent replication either. AI assistance is disclosed. The data and code are not public yet, so it isn't independently reproducible today.

**Why the effect is still believable.** The drops are huge — more than 80 points, with vanishingly small p-values. A drop that large is too big for the known weaknesses — non-independent runs, an AI judge — to explain away. The recovery test is the strongest part. Caution comes back after a cue that names none of the scoring criteria, which makes "suppressed, not absent" the simplest reading.

**Where to hold back.** The author flags the weak spots himself. The AI judge was one of the judged models, so self-preference can't be ruled out. The repeated runs were treated as independent, so the precise p-values overstate certainty. The 0.5% figure is exploratory, and the recovery prompt ran in the same session as the original answer — not a clean isolated test. Scope is narrow too: six scenarios, one domain, one prompt pair. <!-- noev: 0.5% cited under "What they found" -->

**Do the conclusions follow?** At the level the author states them, yes. The suppression and the recoverability are well supported. The "no difference between models" result is a weak null on a small sample, so don't read it as "all models behave identically." The organizational-risk and audit-design ideas are labeled as theory, not findings.

## So what — for you

If AI output feeds a real decision, assume any cause-and-effect claim made in "helpful advice" mode is suspect until it's re-checked.

1. **Add a causal second pass on anything that drives a decision.** The fix is low-effort: a follow-up prompt like *"reconsider this from the perspective of cause and effect"* brought caution back most of the time. Wire it in as an automatic second call — don't rely on someone remembering to ask. <!-- noev: recovery figures cited under "What they found" -->
2. **Split "propose" from "audit."** Use one AI call to suggest what to do. Use a second — with the causal-reconsideration prompt — to check whether the advice rests on a real cause or only a correlation. Don't let one helpful-mode answer do both.
3. **Test on advice-shaped prompts, not analysis-shaped ones.** If your evaluations use clean analytical questions, you're measuring the near-100% case and will badly overestimate how careful the AI is in real use. <!-- noev: figures cited under "What they found" -->
4. **Don't read a confident "because A causes B" as confidence in the cause.** A confident "because A causes B" in an AI recommendation doesn't mean the causal link holds. Discount it until it's passed a reconsideration prompt.
5. **Don't expect to dodge this by switching vendors.** All four models showed it. It's a shared behavior, not a one-model quirk.

## The fine print

- **The percentages aren't model constants.** They're tied to specific model versions, default settings, one prompt pair, and Japanese-language prompts. "This model is careful 17% of the time" is not a number to carry around — use the size of the effect, not the digits. <!-- noev: figure cited under "What they found" -->
- **The domain is narrow.** Nothing here was tested in medicine, finance, policy, or marketing — the high-stakes causal domains. The author names this as the key open question.
- **The cross-model result isn't a vendor ranking** or proof the models are equivalent — it's an underpowered null.
- **0.5% isn't an established rate.** It's a post-hoc, exploratory figure from a single split. <!-- noev: figure cited under "What they found" -->
- **It's about behavior, not internals.** The study measures what models output, not why. "Suppression" is a description of the behavior, not a claim about mechanism.
- **The governance cascade and multi-agent audit design are theory**, not results — the experiment motivates them but doesn't test them.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Okumura (Mitsubishi Research Institute / Kobe University) — *When Helpfulness Overrides Causal Caution: Context-Dependent Suppression and Recovery in LLMs*, 2026.** Across four models and 480 trials, causal caution held in 91.7-100.0% of academic-framed responses but only 6.7-18.3% under practical-advice framing; a single reconsider-from-a-causal-perspective prompt restored it to 71.4-100.0%. [View source](https://arxiv.org/abs/2606.24370){#ev-okumura-causal-caution-2026} · verified 2026-06-29 · primary
