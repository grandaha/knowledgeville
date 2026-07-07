---
type: Concept
title: "Building a Method, Not a Lucky Prompt"
description: "Turning a one-off prompt that happened to work into a documented method you can run again with confidence."
tags: [ai-assisted-data-analysis, repeatability]
timestamp: "2026-07-07"
---

## What makes a prompt lucky rather than reliable

A prompt that produced a good result once may have worked for a reason that has nothing to do with the prompt itself. The file happened to be clean. The question happened to match the exact structure of that particular dataset. The tool happened to run real code that day, rather than pattern-matching from a sample, as [What AI Is Actually Doing With Your Data](/ai-assisted-data-analysis/what-ai-is-actually-doing-with-your-data.md) covers. None of these are properties of the prompt. They are properties of that one dataset, on that one day.

A method is different from a lucky prompt in one specific way. It names the conditions under which it is expected to work, not just the instruction that produced a good result once. If you cannot state what has to be true for your prompt to work again, you do not yet have a method. You have a result you got once.

## The parts of a method worth writing down

A documented method needs four things, and a single successful prompt usually only gives you the first one.

**The exact question or instruction**, phrased the way [Asking Good Analytical Questions](/ai-assisted-data-analysis/02-doing-the-analysis/asking-good-analytical-questions.md) recommends. It should be specific enough to produce one checkable answer, not an open-ended summary.

**What the data has to look like before you run it**: which columns must exist, and what format they need to be in. Note any preprocessing step from [Preparing Your Data Before You Ask](/ai-assisted-data-analysis/01-getting-your-data-in/preparing-your-data-before-you-ask.md) the method depends on.

**The verification step that goes with it.** [Silent Arithmetic and Logic Errors](/ai-assisted-data-analysis/02-doing-the-analysis/silent-arithmetic-and-logic-errors.md) covers a recomputation habit that catches a wrong answer even when the code ran. Name exactly which number to check, and how, every time the method runs.

**What the output should look like when it has actually worked**, so a wrong-shaped result is obvious before you trust it.

## A minimal template to start from

A method does not need to be long to be real. The four items above fit in four short lines: the prompt, the data requirements, the verification step, and the expected output. Capture them the first time a prompt works well enough that you expect to use it again. The next section covers the test that tells you whether what you captured actually holds. Run it against a dataset that is not the one you wrote it for.
