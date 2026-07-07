# Update Log

## 2026-07-07
* **Update**: A bundle-wide reasoning-panel review (domain skeptic, cold reader, and
  AI/ML feasibility personas) ran against all eleven authored pages now that the bundle
  is complete. It confirmed the central thesis -- that running real code is necessary
  but not sufficient for a trustworthy answer -- holds up across all three tracks, and
  found the evidence base genuinely drives the content rather than decorating it. It
  also surfaced four fixable gaps, addressed here: a scoping clarification on
  [Why Dumping a File Rarely Works](/ai-assisted-data-analysis/01-getting-your-data-in/why-dumping-a-file-rarely-works.md)
  (a documented OpenAI row limit applies to a developer API, not the ChatGPT app most
  readers actually use); a signpost in
  [Making It Repeatable](/ai-assisted-data-analysis/03-making-it-repeatable/index.md)
  explaining why that section carries no citations; a model-independent verification
  step added to
  [From Raw Numbers to a Defensible Conclusion](/ai-assisted-data-analysis/02-doing-the-analysis/from-raw-numbers-to-a-defensible-conclusion.md);
  a precision fix to how three different benchmarks are compared on
  [Silent Arithmetic and Logic Errors](/ai-assisted-data-analysis/02-doing-the-analysis/silent-arithmetic-and-logic-errors.md);
  and a one-line guard on
  [Testing Your Method on a New Dataset](/ai-assisted-data-analysis/03-making-it-repeatable/testing-your-method-on-a-new-dataset.md)
  clarifying that passing the test twice does not retire the method's own verification step,
  since a model's output can still vary between runs.
* **Creation**: Authored [Testing Your Method on a New Dataset](/ai-assisted-data-analysis/03-making-it-repeatable/testing-your-method-on-a-new-dataset.md),
  completing [Making It Repeatable](/ai-assisted-data-analysis/03-making-it-repeatable/index.md)
  and, with it, the entire bundle — why a method that worked once has not yet
  proven anything, what makes a second dataset a genuine test rather than a
  repeat of the first (a larger file, a different format, missing values or a
  different structure), and the pass-or-fail check that tells you whether a
  documented method has actually earned the word repeatable.
* **Creation**: Authored [Building a Method, Not a Lucky Prompt](/ai-assisted-data-analysis/03-making-it-repeatable/building-a-method-not-a-lucky-prompt.md) —
  for the reader who runs a recurring analysis rather than a one-off, what
  separates a prompt that happened to work once from a documented method that
  names the conditions it depends on. Covers the four parts of a method worth
  writing down (the exact question, the data requirements, the verification
  step, and the expected output) and a minimal template to capture them in.

## 2026-07-06
* **Creation**: Authored [Silent Arithmetic and Logic Errors](/ai-assisted-data-analysis/02-doing-the-analysis/silent-arithmetic-and-logic-errors.md),
  completing [Doing the Analysis](/ai-assisted-data-analysis/02-doing-the-analysis/index.md) — the
  bundle's sharpest documented example of why running real code against real data is
  necessary but not sufficient for a trustworthy answer. Three separate benchmarks measure
  this failure from three angles: how often it happens (reasoning errors were the largest
  error category measured, well ahead of fabrication), the mechanism behind it (choosing
  the right strategy but the wrong specific method within it), and the ceiling it imposes
  even under close to ideal conditions (frontier models with full code execution still
  scored below fifty percent on a financial-analysis benchmark). Closes with a two-method
  recomputation habit that catches the exact failure this page documents.
* **Creation**: Authored [Where AI Fabricates Data and Numbers](/ai-assisted-data-analysis/02-doing-the-analysis/where-ai-fabricates-data-and-numbers.md) —
  a documented, benchmark-by-benchmark account of AI inventing data points that were
  never in the source, distinct from the arithmetic-error failure mode the next page
  covers. Researchers building code-interpreter and data-analysis benchmarks have
  built fabrication detection directly into their evaluation taxonomies, and the
  honest finding across three separate studies is that fabrication is a real,
  specifically measured category, but not the dominant way an AI-assisted analysis
  goes wrong once real code execution is involved.
* **Creation**: Authored [From Raw Numbers to a Defensible Conclusion](/ai-assisted-data-analysis/02-doing-the-analysis/from-raw-numbers-to-a-defensible-conclusion.md) —
  the gap between a summary, which restates what the data shows, and a conclusion,
  which claims why. Covers a chain of follow-up questions that tests whether a
  conclusion survives scrutiny, a compact correlation-is-not-causation check before
  accepting a trend, and when to stop questioning the model and verify a piece of
  the conclusion against the source data directly.
* **Creation**: Authored [Asking Good Analytical Questions](/ai-assisted-data-analysis/02-doing-the-analysis/asking-good-analytical-questions.md) —
  the difference between a summary request, which invites an open-ended description with
  nothing to check it against, and an analytical question, which has one specific,
  checkable answer. Covers a before-and-after worked example and the follow-up-question
  habit that tests whether an answer came from real computation or a plausible guess.
* **Creation**: Authored [A Landscape of AI Data Analysis Tools](/ai-assisted-data-analysis/01-getting-your-data-in/a-landscape-of-ai-data-analysis-tools.md),
  completing [Getting Your Data In](/ai-assisted-data-analysis/01-getting-your-data-in/index.md) —
  extending the real-computation-versus-plausible-answer test past chat tools to AI features
  embedded in business intelligence dashboards and in spreadsheets themselves. Microsoft's
  Power BI Copilot runs real queries against a live data model, but only once that model
  has been explicitly prepared for AI use; Copilot in Excel writes real, functioning formulas
  into a live workbook rather than describing an answer. Both carry the vendor's own
  instruction to verify the result before trusting it.
* **Creation**: Authored [Code Interpreters vs. Plain Chat](/ai-assisted-data-analysis/01-getting-your-data-in/code-interpreters-vs-plain-chat.md) —
  what each mode actually does with your file, and why running real code against
  it is necessary but not sufficient for a trustworthy answer. A benchmark testing
  frontier models with a real code-execution tool against actual financial
  spreadsheets found the strongest models still scored below fifty percent, since
  the failure was in what code the model chose to write, not in whether code
  executed at all.
* **Creation**: Authored [Preparing Your Data Before You Ask](/ai-assisted-data-analysis/01-getting-your-data-in/preparing-your-data-before-you-ask.md) —
  what to actually do before uploading a file, since no major vendor documents a
  built-in way to confirm a file was read in full after the fact. Covers using a
  documented page limit and a free token-counting endpoint as a proactive check,
  splitting large files and spreadsheets before upload rather than trusting a
  silent row cap, and converting Excel and PDF sources to a plain CSV where the
  underlying data allows it.
* **Creation**: Authored [Why Dumping a File Rarely Works](/ai-assisted-data-analysis/01-getting-your-data-in/why-dumping-a-file-rarely-works.md),
  the bundle's first full page — a documented, vendor-by-vendor account of why
  uploading a file and asking an AI tool to "analyze this" does not reliably process
  the whole dataset, covering context-window limits, three different documented
  overflow behaviors, and the added risk that Excel and PDF formats carry beyond a
  plain CSV.
* **Creation**: Scaffolded the bundle — practical guidance on analyzing data with AI
  properly, across three tracks:
  [Getting Your Data In](/ai-assisted-data-analysis/01-getting-your-data-in/index.md),
  [Doing the Analysis](/ai-assisted-data-analysis/02-doing-the-analysis/index.md),
  and [Making It Repeatable](/ai-assisted-data-analysis/03-making-it-repeatable/index.md).
  Ten planned pages await authoring.
* **Update**: A bundle-wide reasoning-panel review (domain skeptic, cold reader, and
  AI/ML feasibility personas) ran against the scaffolded design before any page was
  authored. It found the original five-track structure buried the bundle's single most
  useful insight — that running real code against your data makes an answer auditable,
  not automatically correct — behind three tracks of more generic advice, and that a
  tools-comparison track and a verification track both belonged closer to where the data
  first enters the workflow and where an analysis is first questioned. Restructured to
  three tracks in response: tool-choice and ingestion mechanics moved together, and
  verification content moved earlier so it sits with the analysis technique itself
  rather than trailing behind it. One planned page (a standalone page on cherry-picked
  trends and false causation) was folded into a checklist within a related page instead
  of shipping as its own thin page.
