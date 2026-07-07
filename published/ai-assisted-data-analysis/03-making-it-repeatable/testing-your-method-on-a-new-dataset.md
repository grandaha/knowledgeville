---
type: Concept
title: Testing Your Method on a New Dataset
description: "Why a method that worked once needs a second, different dataset before you trust it as repeatable."
tags: [ai-assisted-data-analysis, repeatability]
timestamp: "2026-07-07"
---

## Why one success does not prove a method

A method documented the way [Building a Method, Not a Lucky Prompt](/ai-assisted-data-analysis/03-making-it-repeatable/building-a-method-not-a-lucky-prompt.md) describes still rests on one data point: the dataset you wrote it against. Writing the method down proves you can describe what worked. It does not prove the description holds for anything other than the file already in front of you.

The only way to tell a real method from a documented coincidence is to run it somewhere else. If the method only works on the dataset it was written for, it was never a method. It was a precise description of one lucky result.

## What different enough actually means

A second dataset does not count as a real test if it is nearly identical to the first. Change something that could actually break the method. A larger file, closer to the size limits [Why Dumping a File Rarely Works](/ai-assisted-data-analysis/01-getting-your-data-in/why-dumping-a-file-rarely-works.md) covers, tests whether the whole file still arrives intact. A different format tests whether the preprocessing step in your written method still applies. A dataset with missing values, extra columns, or a slightly different structure tests something else again. It reveals whether the method's assumptions actually held, or just happened to hold once.

Pick at least one of these differences deliberately for the test, rather than grabbing the next convenient file. A second dataset that shares every relevant property with the first is not a second test. It is the same test, run twice.

## A simple pass or fail check

Run the documented method exactly as written against the new dataset. Do not adjust the prompt to compensate for something that looks off. Check the same verification step named in the method, on this new data, and compare it against what the method's expected output describes. If either one fails, the method needs a revision, not a one-time fix applied quietly and forgotten. If the verification step passes and the output matches the documented shape, on a dataset genuinely different from the first, the method has earned it. It is repeatable, not just lucky.
