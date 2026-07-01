---
type: Reference
title: The Great Value Migration
description: "An investment thesis that as AI intelligence gets cheap, value migrates from selling compute to owning and orchestrating it — favoring the hyperscalers."
resource: "https://x.com/i/status/2071932670788198687"
tags: [strategy-and-investment, industry-brief]
timestamp: "2026-07-01"
---

- **Title:** The AI Economy: The Next Chapter (a four-part article)
- **Author:** Ricky Ho ([@rickyho_1989](https://x.com/rickyho_1989)) — CIO/PM at a single-family office, and a former sell-side equity research analyst
- **Publication:** Posted as a long-form article on X
- **Date:** June 30, 2026
- **Who it's really for:** Public-market investors deciding where AI profits will land. Secondarily, leaders choosing which layer of the AI stack to bet their organization on
- **Link:** [x.com](https://x.com/i/status/2071932670788198687)

## The one-line takeaway

As intelligence gets cheap, the money moves. Not to whoever builds the smartest model, but to whoever owns the infrastructure and the routing layer that every model runs through.

## The argument

**The thesis.** The industry is quietly shifting from optimizing for *intelligence* to optimizing for *intelligence per dollar*. Once that happens, the profit stops accruing to the smartest model and starts accruing to whoever owns the pipes ([Ricky Ho, 2026](#ev-rickyho-ai-economy-2026)).

**The reasoning, in four moves:**

1. **Intelligence is becoming a commodity.** Enterprises reached for frontier models while they were still asking "does this even work?" That phase is ending. As finance teams start scrutinizing AI budgets, the goal flips from "smartest" to "cheapest model that clears the bar." Ho calls this AI's "Linux moment": open-weight models don't need to beat every frontier model — just be good enough for most work.

2. **Value migrates from selling compute to owning it.** The market pays for whoever sells the next GPU. Ho argues the better question is who owns the *last* one. Cheaper inference means installed hardware does more work. So the value shifts from one-time chip sales to the recurring cash flow of infrastructure already sitting inside the big clouds.

3. **Orchestration becomes the moat.** No enterprise standardizes on a single model, just as none runs a single database. They route each task to the cheapest model that clears the bar, and escalate only the hard ones. Once that routing layer holds the retrieval pipelines, evals, security policies, and audit trails, the model underneath becomes a swappable part. The platform becomes the thing you can't easily leave.

4. **Geopolitics pushes the same way.** As governments treat frontier models as strategic assets, availability starts to differ by country. A multinational can't run its AI on one provider that might be restricted in one region. That makes compliance-aware routing more valuable — and the global clouds already have the compliance machinery.

**The conclusion.** The first chapter of AI was about *inventing* intelligence. The next, Ho argues, is about *distributing* it cheaply, securely, and at scale — which favors the infrastructure and orchestration layer over the model builders. He closes with his actual book: long Nvidia, TSMC, SK Hynix, Micron, Samsung, Microsoft, Alphabet, Amazon, and Meta.

## The evidence behind it

Most of the load is carried by analogy and reasoning, not new data. The figures Ho cites are borrowed from third parties, so we traced each to its original.

**Inference cost is collapsing** (the foundation of the whole thesis):

- The cost to run a model at GPT-3.5-level quality fell more than **280-fold** between late 2022 and late 2024 — from about $20 to $0.07 per million tokens ([Stanford HAI, 2025](#ev-stanford-ai-index-2025-cost-280x)). *(Traced to the Stanford AI Index; the article's framing is faithful.)*
- Andreessen Horowitz puts the rate at roughly **10x cheaper per year** for a fixed level of capability ([a16z, 2024](#ev-a16z-llmflation-10x)). *(Traced to a16z's "LLMflation" analysis.)*
- Epoch AI finds the same direction but a wider, faster range: a **median near 50x per year** across benchmarks ([Epoch AI, 2025](#ev-epoch-inference-price-2025)). *(Traced to Epoch. Note this is faster than a16z's 10x, not "similar," as the article implies.)*
- OpenAI's CFO said inference cost fell about **97%** from GPT-4 to the latest generation in roughly two years ([Sarah Friar, 2026](#ev-openai-friar-inference-97pct)). *(Her words on a podcast; anchor on "GPT-4 to latest," not a specific successor model.)*
- Sam Altman relayed the customer complaint now driving demand: "My company spent my entire 2026 budget in Q1. Can you make this more efficient?" ([Sam Altman, 2026](#ev-altman-2026-budget-q1)). *(A real on-stage remark, via reporting; the "efficient, not smarter" framing is Ho's gloss.)*

**Smaller models are catching up:**

- Meta already runs a giant foundation model as a *teacher* and distills it into smaller models that serve ads at scale ([Meta, 2025](#ev-meta-exfm-distillation-2025)). *(Traced to Meta's own research paper — the clearest evidence for the "good enough, far cheaper" claim.)*

**Governments are stepping in:**

- A US executive order sets up a *voluntary* pre-release review of frontier models with advanced cyber capabilities ([White House, 2026](#ev-whitehouse-eo-14409-2026)). It is explicitly not a mandatory license. *(Traced to the order itself; the article's read is accurate.)*
- Ho's lead example, export controls on Anthropic's top models, is already stale. They were imposed in mid-June 2026 ([CSIS, 2026](#ev-anthropic-export-controls-2026)) and lifted around June 30 ([CNBC, 2026](#ev-anthropic-export-controls-lifted-2026)). *(A real episode, but reversed within days of the article; see the trust note below.)*

## How much to trust it

Slow down here. This is the section that matters most for this piece.

**The author is long everything he's recommending.** Ho is a family-office portfolio manager. He ends with an explicit book: long Nvidia, the memory makers, and the big clouds ([Ricky Ho, 2026](#ev-rickyho-ai-economy-2026)). He profits if the market comes to believe it. That doesn't make it wrong, but read it as a well-argued position from someone with money on the outcome, not as neutral analysis.

**The argument is built to win either way.** Ho lays out two futures — models get more efficient, or demand explodes — and concludes both are good for the hyperscalers. An argument where every scenario points to the same answer is worth an extra look. It may be right, but it's hard to falsify.

**The sources don't fully agree.** Ho stacks Stanford, a16z, and Epoch as if they say the same thing. They agree on direction: inference is getting cheaper fast. But they don't agree on magnitude — 10x a year versus a median closer to 50x ([a16z, 2024](#ev-a16z-llmflation-10x); [Epoch AI, 2025](#ev-epoch-inference-price-2025)). Friar's own 97% over two years is slower still, roughly 6x a year ([Sarah Friar, 2026](#ev-openai-friar-inference-97pct)). The trend is real; the precise rate is not settled.

**The freshest example already broke.** The Anthropic export-control story was reversed within days of publication ([CNBC, 2026](#ev-anthropic-export-controls-lifted-2026)). That's a caution about the geopolitics leg specifically: policy here is volatile, and a thesis that leans on it inherits that volatility.

What holds up well: the core mechanism. Cheaper inference really does shift value toward whoever owns and coordinates the compute. And Meta's teacher-student setup is real, primary-sourced proof that "good enough and far cheaper" is already in production ([Meta, 2025](#ev-meta-exfm-distillation-2025)).

## So what — for you

If you buy or run AI rather than trade it, four things follow:

- **Assume inference keeps getting cheaper.** Don't lock into today's prices or over-build around a model because it's cheapest this quarter. The floor is still dropping.
- **Design for portability, not loyalty.** Ho's strongest practical point: the switching cost lives in the orchestration layer, not the model. Keep your prompts, evals, and data pipelines model-agnostic so you can move.
- **Watch where the lock-in accrues.** The cloud and routing platform is where you'll get stuck, not the model. That's the relationship to negotiate hardest and keep an exit from.
- **If you're multinational, compliance-aware routing is a real advantage.** Model availability now varies by country. The ability to reroute workloads by jurisdiction is worth planning for, not bolting on later.

## The fine print

This is an investment thesis written for public-market investors, not an enterprise playbook. The stock list at the end is the author's own position. We report it to show his stake, not as advice — nothing here is a recommendation to buy or sell anything.

It's also a snapshot. Ho wrote it on June 30, 2026, and the cost figures and policy details move fast — one already reversed the day after. When a decision rides on a specific number, go to the traced source and check it yourself.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Ricky Ho (@rickyho_1989), single-family-office CIO/PM — *The AI Economy: The Next Chapter (four-part article)*, 2026.** the variable that ultimately determines where profits accrue... is unlikely to be intelligence itself, but rather the amount of intelligence delivered for every dollar spent. [View source](https://x.com/i/status/2071932670788198687){#ev-rickyho-ai-economy-2026} · verified 2026-07-01 · primary
- **Stanford Institute for Human-Centered AI (HAI) — *The 2025 AI Index Report (State of AI in 10 Charts)*, 2025.** dropped from $20 per million tokens in November 2022 to just $0.07 per million tokens by October 2024 (Gemini-1.5-Flash-8B) — a more than 280-fold reduction in approximately 18 months. [View source](https://hai.stanford.edu/news/ai-index-2025-state-of-ai-in-10-charts){#ev-stanford-ai-index-2025-cost-280x} · verified 2026-07-01 · primary
- **Andreessen Horowitz (Guido Appenzeller) — *Welcome to LLMflation — LLM inference cost is going down fast*, 2024.** For an LLM of equivalent performance, the cost is decreasing by 10x every year. [View source](https://a16z.com/llmflation-llm-inference-cost/){#ev-a16z-llmflation-10x} · verified 2026-07-01 · primary
- **Epoch AI — *LLM inference prices have fallen rapidly but unequally across tasks*, 2025.** between 9x to 900x per year... with a median of 50x per year. The price to achieve GPT-4's performance on a set of PhD-level science questions fell by 40x per year. [View source](https://epoch.ai/data-insights/llm-inference-price-trends){#ev-epoch-inference-price-2025} · verified 2026-07-01 · primary
- **OpenAI CFO Sarah Friar (All-In Podcast) — *OpenAI CFO Sarah Friar: IPO, AI Rivalries, New Device, and Spending $100B+ on Compute*, 2026.** from 4 to 5.4, it was 97%, but that happened in like 2 years. [View source](https://podcasts.happyscribe.com/all-in-with-chamath-jason-sacks-friedberg/openai-cfo-sarah-friar-ipo-ai-rivalries-new-device-and-spending-100b-on-compute){#ev-openai-friar-inference-97pct} · verified 2026-07-01 · ⚠ secondary mirror
- **Sam Altman, OpenAI (Intelligence at Work event; reported by Tom's Hardware/Axios) — *OpenAI CEO Sam Altman admits AI token costs are becoming a huge issue*, 2026.** My company spent my entire 2026 budget in Q1. Can you make this more efficient? [View source](https://www.tomshardware.com/tech-industry/artificial-intelligence/openai-ceo-sam-altman-admits-ai-token-costs-are-becoming-a-huge-issue-company-seeks-improved-value-as-overspending-becomes-a-meme){#ev-altman-2026-budget-q1} · verified 2026-07-01 · ⚠ secondary mirror
- **Meta (Liang, Liu, Jin et al.) — *External Large Foundation Model: How to Efficiently Serve Trillions of Parameters for Online Ads Recommendation (WWW 2025)*, 2025.** a foundation model can serve multiple students as vertical models to amortize its building cost, using external distillation to transfer knowledge from the large teacher to smaller student models. [View source](https://arxiv.org/abs/2502.17494){#ev-meta-exfm-distillation-2025} · verified 2026-07-01 · primary
- **The White House — *Executive Order 14409 — Promoting Advanced Artificial Intelligence Innovation and Security*, 2026.** Nothing in this section shall be construed to authorize the creation of a mandatory governmental licensing, preclearance, or permitting requirement for the development, publication, release, or distribution of new AI models. [View source](https://www.whitehouse.gov/presidential-actions/2026/06/promoting-advanced-artificial-intelligence-innovation-and-security/){#ev-whitehouse-eo-14409-2026} · verified 2026-07-01 · primary
- **CSIS (reporting/analysis) — *The Department of Commerce Restricted Access to Anthropic's Latest Models. What Comes Next?*, 2026.** the Department of Commerce restricted access to Anthropic's latest models. [View source](https://www.csis.org/analysis/department-commerce-restricted-access-anthropics-latest-models-what-comes-next){#ev-anthropic-export-controls-2026} · verified 2026-07-01 · ⚠ secondary mirror
- **CNBC — *Anthropic says Trump admin has lifted export controls*, 2026.** Anthropic says Trump admin has lifted export controls. [View source](https://www.cnbc.com/2026/06/30/anthropic-says-trump-admin-has-lifted-export-controls-on-claude-fable-5-and-mythos-5.html){#ev-anthropic-export-controls-lifted-2026} · verified 2026-07-01 · ⚠ secondary mirror
