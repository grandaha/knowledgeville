---
type: Reference
title: Glossary
description: Plain-language definitions of the terms used across this bundle.
tags: [glossary, reference]
timestamp: "2026-09-19"
appendix: true
generated:
  by: claude-code/claude-opus-4.8
  at: "2026-07-01T00:00:00Z"
---

Plain-language definitions of the terms this bundle uses. It grows as the bundle does.

- **Acceptance test**: a written description of what a usable result looks like for one type of job, set down before any model is tried, so every result is judged the same way.
- **Answer key**: a right answer that knowledge can be checked against automatically, such as working code, a system setting, or a database query result. Policies and judgment have none.
- **Chargeback**: passing the actual cost of AI use to the business unit that incurred it, so the cost comes out of that unit's budget.
- **Cost per accepted result**: everything spent to get usable output, including failed attempts and the time people spend checking and fixing, divided by the number of results that passed the acceptance test.
- **Criteria**: the handful of factors that should actually drive the decision, as opposed to everything you could consider.
- **Decision guide**: a page that helps you make one recurring, consequential decision: the options, the criteria, the tradeoffs, and when each choice wins.
- **Deflection**: a case an automated step handled on its own, without reaching a person. Counting a deflection as a resolution overstates the saving, because the customer may come back through another channel.
- **Fine-tuning**: training a supplier's model further on your own labelled examples, so it learns your pattern. The result runs on the supplier's base model and stops working when that base model is retired.
- **FinOps**: the practice of managing technology spending, first cloud and now AI, by making costs visible and assigning them to the teams that incur them.
- **Knowledge-Centered Success (KCS)**: a practice from customer support in which the people who use knowledge articles also fix or flag them as they go. It was formerly called Knowledge-Centered Service.
- **Labelled examples**: past cases where someone recorded the right answer. Often already held in an operational system, such as the queue each resolved ticket ended up in.
- **Last-verified date**: the date someone last confirmed that a piece of knowledge is still true. It protects you only if the system acts on it.
- **Open-weight model**: an AI model whose trained weights are published for anyone to download and run. Its license may still limit how it can be used, so open-weight is not the same as open source.
- **Pay-per-use spend**: AI charged by the unit of use, usually per token, through APIs, coding agents, and automations. The bill rises and falls with use.
- **Precision and recall**: two ways of being wrong. Precision asks how many of the cases a system flagged were genuine; recall asks how many of the genuine cases it caught. F1 combines the two into one figure.
- **Reversibility**: how cheaply you can undo a choice if it turns out wrong; cheap-to-reverse decisions deserve less deliberation.
- **Routing**: sending different requests to different AI models. It can mean a person assigning a model to each type of work, software choosing a model for each request, or a backup model taking over when the first is unavailable. A related arrangement, a cascade, runs a cheap option first and passes only what it cannot finish to a more expensive one.
- **Seat license**: a fixed monthly price per person for an AI tool. The bill stays the same whether the person uses it daily or never.
- **Semantic layer**: a defined set of business measures, such as revenue or active customers, that an AI can query. It can decline questions outside its definitions.
- **Showback**: reporting AI costs to the teams that incurred them without charging those teams. A central budget still pays.
- **Threshold**: the score above which an automated decision is acted on. A trained model returns a score rather than a yes or no, so a person chooses this number, against a particular set of data, on a particular date.
- **Token**: a fragment of a word. AI models read and write in tokens, and pay-per-use pricing counts them.
- **Total cost of ownership (TCO)**: the full lifetime cost of an option, not just the upfront price. It includes maintenance, support, and the cost of your own time.
- **Tradeoff**: what you give up by choosing one option over another; the guides cite the evidence behind the important ones.
- **When each wins**: the conditions under which a given option is the better call, written as plain "if your situation is X, lean toward Y."
