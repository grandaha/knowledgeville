# Change log — Decision Guides

## 2026-09-19

* **Creation**: new guide, [Does This Need a Language Model?](/decision-guides/does-this-need-a-language-model.md):
  what should make a recurring automated decision, comparing a rule, a model trained on your own
  examples, a general language model, and two of those working together. It puts two cheaper steps
  first, measuring the current cost and writing rules for the obvious cases, and shows that ten
  labelled examples per category carried a trained model most of the way to its full-data accuracy
  on a 77-answer benchmark. It also records that when a classifier's accuracy collapsed under a
  shift, recalibrating its threshold on a small sample recovered most of the loss without retraining,
  and that one provider's retirement left customers unable to run models they had already trained.
  The guide also records that rules are cheap to run and expensive to keep, citing a 30 to 50% failure
  rate for an earlier generation of rule-based automation.
* **Update**: [Glossary](/decision-guides/glossary.md) adds deflection, fine-tuning, labelled examples,
  precision and recall, and threshold, and extends routing to cover a cascade.
* **Update**: [Which AI Model for Which Job](/decision-guides/which-ai-model-for-which-job.md) now points
  readers at the prior question, whether the work needs a language model at all.

## 2026-09-13

* **Creation**: new guide, [Keeping What Your AI Knows True](/decision-guides/keeping-what-your-ai-knows-true.md):
  how to keep the knowledge your AI assistants and agents act on current, owned, and safe. It sorts
  knowledge by whether a machine can check it, and compares reviewing on use, reviewing on a schedule,
  letting AI maintain it, and answering only from reviewed sources. It notes that in the two court
  rulings found, the source content was correct and the AI still got it wrong.
* **Update**: [Glossary](/decision-guides/glossary.md) adds answer key, Knowledge-Centered Success
  (KCS), last-verified date, and semantic layer.
* **Creation**: new guide, [Who Should Own the AI Bill](/decision-guides/who-should-own-the-ai-bill.md):
  who should hold each kind of AI spend, seat licenses and pay-per-use charges, and which budget
  controls help without choking the adoption you are paying for. It shows that seats hide use, that
  pay-per-use spend is visible only to whoever builds the tracking, and that no study shows charging
  business units changes how they use AI.
* **Update**: [Glossary](/decision-guides/glossary.md) adds chargeback, FinOps, pay-per-use spend,
  seat license, showback, and token.
* **Creation**: new guide, [Which AI Model for Which Job](/decision-guides/which-ai-model-for-which-job.md):
  whether a team's recurring AI work should run on one model, a model per type of work, a router
  that picks for each request, or an open-weight model. It explains why a listed price is not the
  real cost, why being able to switch matters more than any single choice, and gives a 20-task
  pilot for testing the decision on your own work.
* **Update**: [Glossary](/decision-guides/glossary.md) adds acceptance test, cost per accepted
  result, open-weight model, and routing.

## 2026-08-04

* **Creation**: new guide — [When to Embed an Engineer](/decision-guides/when-to-embed-an-engineer.md):
  whether a stalled AI project needs an embedded "forward deployed" engineer, an outside firm, or
  a better handoff. Covers the scope condition that makes embedding worth its cost, why deep context
  usually beats fast starts for internal work, who maintains what gets built, and the compensation
  and reporting-line traps that surface after a search has already run.

## 2026-07-05

* **Update**: [Build vs. Buy](/decision-guides/build-vs-buy.md) adds a new section, "When the
  capability is an AI system" — fine-tuning a foundation model still depends on that vendor
  (no downloadable weights, no independence from the vendor's own deprecation schedule),
  AI usage is typically billed per token rather than a flat subscription, and both build and
  buy carry an ongoing evaluation burden for factually wrong output that traditional software
  doesn't have.

## 2026-07-01

* **Creation**: new guide — [When to Let AI Do It](/decision-guides/when-to-let-ai-do-it.md): whether to hand a task to AI or do it yourself, where AI earns its keep, and when to keep a human in the loop.
* **Creation**: new bundle — cited, plain-language guides for the recurring, consequential decisions a knowledge worker faces, opening with [How These Guides Work](/decision-guides/how-these-guides-work.md).
* **Creation**: first guide — [Build vs. Buy](/decision-guides/build-vs-buy.md): whether to build a capability in-house or buy it off the shelf, with the options, the sourced tradeoffs, and when each one wins.
