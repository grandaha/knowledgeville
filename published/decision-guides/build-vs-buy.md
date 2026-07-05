---
type: Decision
title: Build vs. Buy
description: "How to decide whether to build a capability yourself or buy it off the shelf — the options, the tradeoffs, and when each one wins."
tags: [decision-guides, strategy]
timestamp: "2026-07-05"
---

## The decision

You need a capability — a tool, a system, a feature — and you can either build it yourself or buy something that already exists. This guide helps you make that call. It's faced by anyone choosing how to get a capability: a founder, a team lead, or a leader signing off on the spend.

## Does this apply to you?

Use this when **both paths are genuinely real** — a credible off-the-shelf option exists, *and* building it yourself is feasible. If no product fits your need, or you have no way to build and maintain one, you don't really have this decision. It also applies to the middle ground: buying a base and extending it.

## The options

Most real choices sit on a spectrum, not a binary:

- **Buy** — adopt an existing product or service (a SaaS tool, a vendor, an off-the-shelf system), and configure it to your needs.
- **Build** — create it yourself, with your own team or contractors.
- **Buy and extend** — take a commodity base and add your own layer on top, where your edge is in the integration or configuration.

## What actually matters

A handful of criteria should drive this. Most other considerations are noise:

- **Is it your differentiator?** Does this capability set you apart from competitors, or is it just table stakes?
- **Time to value** — how soon you need it working, and what waiting costs you.
- **Total cost of ownership** — the whole lifetime cost, not the sticker price.
- **Control and fit** — how much you need to shape the data, the roadmap, and the details.
- **Risk and reversibility** — how likely each path is to go wrong, and how cheaply you can change your mind.
- **Your capacity** — whether you can staff *and maintain* a build for its whole life, not just ship it.

## How the options compare

**Differentiation.** This is the first filter. Geoffrey Moore's core-vs-context framework is the useful lens ([Moore, 2000](#ev-moore-core-vs-context-2000)). "Core" is what differentiates you and wins customers. "Context" is everything else you must do but that does not set you apart. Buying a capability makes you, at best, as good as everyone else who bought it — fine for context, fatal for core. Building lets you differentiate — but only pays off if the thing actually is a differentiator.

**Speed.** Buying gets you to value in days or weeks. Building takes months, and usually longer than you think.

**Cost over time.** Buying is a predictable subscription — but it runs forever. Building is a large upfront cost plus a hidden majority. Maintenance typically consumes **40 to 80 percent of a software system's total lifetime cost — about 60 percent on average** ([Glass, 2003](#ev-glass-software-maintenance-2003)). The build does not end at launch; that is where most of the bill starts.

**Risk.** Building is riskier than it looks. Across more than 5,400 large IT projects, the average ran **45 percent over budget and 7 percent over time** ([McKinsey, 2012](#ev-mckinsey-oxford-it-projects-2012)). They delivered **56 percent less value than predicted**, and **17 percent went so badly they threatened the company's existence**. Buying carries a different risk: dependence on a vendor, and the cost of switching later.

**Control.** Building gives you full control of the data, the roadmap, and the details. Buying hands the roadmap to the vendor — but hands the upkeep burden to them too.

## When the capability is an AI system

The criteria above still apply, but when what you're building or buying is an AI system — an
LLM-powered feature, a fine-tuned model, an agent — a few things about "build" and "buy"
themselves change.

**"Build" often still means renting someone else's model.** Fine-tuning a foundation model
gets you a model you call by ID through the vendor's API — "use this model just like you would
the final fine-tuned model" — not a copy of the weights you can run or move elsewhere
([OpenAI, 2026](#ev-openai-finetuning-2026-api-only-access)). The full control this guide's
"Control" criterion assumes "build" gives you doesn't fully apply until you actually own the
weights.

**Deprecation is a new risk category, not covered by ordinary vendor risk.** A vendor can
retire the base model your fine-tune depends on. OpenAI gives "at least 6 months" notice for
generally available models and "at least 3 months" for specialized variants — but "inference
on fine-tuned models will be disabled only when the underlying base model is deprecated"
([OpenAI, 2026](#ev-openai-deprecations-2026-notice-and-cutoff)). Your system can stop working
with no code change on your end, on a timeline you don't control.

**Cost tends to scale with usage, not with team size.** Buying isn't always the flat,
predictable subscription this guide's "Cost over time" section describes — OpenAI's API, like
most AI APIs, is billed per token, so cost rises directly with how much the system actually
gets used, not with seats ([OpenAI, 2026](#ev-openai-pricing-2026-per-token)).

**Both paths carry an ongoing evaluation burden that traditional software doesn't have.** Even
a well-built AI system can produce factually wrong output — Anthropic's own guidance on this is
blunt: "always validate critical information, especially for high-stakes decisions"
([Anthropic, 2026](#ev-anthropic-reduce-hallucinations-2026-standing-risk)). Traditional
software doesn't hallucinate; this is a standing cost that doesn't show up in the maintenance
figure cited above.

## When each one wins

**Buy when:**

- The capability is context, not your differentiator.
- A good-enough product already exists.
- You need it soon, and waiting is expensive.
- You do not have the team to build and, more importantly, maintain it.
- The requirement is common and well-understood, not unusual to you.

**Build when:**

- The capability *is* your competitive differentiation — this is core.
- No product fits, and the gap genuinely matters.
- You have a team that can build it and will still be there to maintain it.
- You need control over data or roadmap that no vendor will give you.

**Buy and extend when:**

- The base is a commodity, but your advantage lives in how you configure or connect it.

## How to decide

Answer these in order, about your own situation:

1. **Is this a differentiator or table stakes?** If it's context, default to buy and stop second-guessing.
2. **Does a good-enough product exist?** If nothing fits, your real choice is build or wait.
3. **How fast do you need it, and what does waiting cost?**
4. **Can you maintain a build for its whole life** — not just ship version one?
5. **How reversible is each path?** A buy you can switch out of cheaply needs little agony; a one-way build needs a lot.

## Watch out for

- **Undercounting the build.** Launch is the small part. Maintenance is the majority of the lifetime cost <!-- noev: Glass, cited under "How the options compare" -->, so a build is a permanent staffing commitment, not a one-time project.
- **Optimism about build risk.** Overruns are the norm, not the exception, and the bad cases are very bad <!-- noev: McKinsey, cited above -->. Budget and plan for it.
- **"We're special."** Most needs are context dressed up as core. Building the commodity thing yourself is the most common way this decision goes wrong.
- **Lock-in on the buy side.** Before you depend on a vendor, check the exit cost, whether you can get your data out, and how healthy the vendor is.
- **Binary thinking.** Build-or-buy is often a false choice — buy-and-extend or a partnership is frequently the better answer.
- **Fine-tuning isn't owning.** If "build" means fine-tuning someone else's foundation model, you're still dependent on that vendor <!-- noev: OpenAI, cited under "When the capability is an AI system" --> — weigh deprecation risk into the build case, not just the buy case.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Geoffrey Moore — *Living on the Fault Line (core-vs-context; later extended in Dealing with Darwin)*, 2000.** Core is anything that contributes directly to competitive differentiation... Context is everything else — all the things that you or your company or product must do to pass muster but which do not differentiate you. [View source](https://geoffreyamoore.com/book/living-on-the-fault-line/){#ev-moore-core-vs-context-2000} · verified 2026-07-01 · primary
- **Robert L. Glass — *Facts and Fallacies of Software Engineering (Fact 41), Addison-Wesley (ISBN 0-321-11742-5)*, 2003.** Maintenance typically consumes 40 to 80 percent (average, 60 percent) of software costs. Therefore, it is probably the most important life cycle phase of software. [View source](https://www.informit.com/store/facts-and-fallacies-of-software-engineering-9780321117427){#ev-glass-software-maintenance-2003} · verified 2026-07-01 · primary
- **McKinsey & Company with the BT Centre for Major Programme Management, University of Oxford — *Delivering large-scale IT projects on time, on budget, and on value*, 2012.** Large IT projects, on average, run 45 percent over budget and 7 percent over time, while delivering 56 percent less value than predicted. [View source](https://www.mckinsey.com/capabilities/tech-and-ai/our-insights/delivering-large-scale-it-projects-on-time-on-budget-and-on-value){#ev-mckinsey-oxford-it-projects-2012} · verified 2026-07-01 · primary
- **OpenAI — *Supervised fine-tuning (API docs)*, 2026.** Use this model just like you would the final fine-tuned model. [View source](https://developers.openai.com/api/docs/guides/supervised-fine-tuning){#ev-openai-finetuning-2026-api-only-access} · verified 2026-07-05 · primary
- **OpenAI — *Model deprecations (API docs)*, 2026.** Fine-tuned models created from these base models are not affected by this deprecation, but you will no longer be able to create new fine-tuned versions with these models... Inference on fine-tuned models will be disabled only when the underlying base model is deprecated. [View source](https://developers.openai.com/api/docs/deprecations){#ev-openai-deprecations-2026-notice-and-cutoff} · verified 2026-07-05 · primary
- **OpenAI — *Pricing (API docs)*, 2026.** Tokens are billed at the chosen model's input and output rates. [View source](https://developers.openai.com/api/docs/pricing){#ev-openai-pricing-2026-per-token} · verified 2026-07-05 · primary
- **Anthropic — *Reduce hallucinations (Claude Platform docs)*, 2026.** Even the most advanced language models, like Claude, can sometimes generate text that is factually incorrect or inconsistent with the given context... Always validate critical information, especially for high-stakes decisions. [View source](https://platform.claude.com/docs/en/docs/test-and-evaluate/strengthen-guardrails/reduce-hallucinations){#ev-anthropic-reduce-hallucinations-2026-standing-risk} · verified 2026-07-05 · primary
