---
type: Playbook
title: Running a Red Team
description: "Scoping an engagement, the objective-based methodology, and a worked example from a frontier lab."
tags: [ai-security-lead, red-teaming]
timestamp: "2026-07-02"
---

Traditional penetration testing asks "can we get in." AI red-teaming asks a different question: "can we get the model to do this specific thing it shouldn't" — leak a document, take an unauthorized action, produce content it was explicitly built to refuse. That shift changes what the engagement looks like.

## Why this isn't just penetration testing with a new label

A traditional pentest has a fixed target with a finite, enumerable attack surface. An LLM is probabilistic — the same prompt can produce a different output on repeat runs, and the "surface" includes the model's training, its instructions, and everything an attacker can say to it. That means a red-team engagement needs objectives, not just techniques: define what you're trying to get the model to do, then test at scale, since a single failed attempt tells you nothing about whether the model is actually resistant.

## Scope it before you start

Set your evaluation plan and capability thresholds *before* testing begins, not after you see what the model does. Anthropic's own framing of why this matters: developing evaluation plans in advance and committing to capability thresholds that would motivate increased security is what lets a lab keep advancing capability while staying ahead of the risk that capability creates ([Anthropic, 2025](#ev-anthropic-frontier-red-team-2025-thresholds-methodology)). Decide what "too dangerous to ship without more controls" looks like before you're the one deciding it in the middle of a launch deadline.

## Test the categories that actually matter for your system

Use the [OWASP Top 10](/ai-accountability/06-ai-security-lead/the-owasp-top-10-for-llms.md) as your baseline coverage, then add domain-specific risks for what your system actually does. A worked example of how fast this can move: in Capture The Flag cybersecurity exercises, Claude went from the level of a high schooler to the level of an undergraduate in a single year ([Anthropic, 2025](#ev-anthropic-frontier-red-team-2025-cybersecurity-progress)). A red-team baseline from a year ago tells you less than you think it does — capability moves fast enough that "we tested this last year" isn't the same as "we tested this."

## Don't red-team in isolation

The most credible AI security functions bring in outside eyes rather than relying entirely on internal review. Anthropic's own program is a useful reference point: it's run technical evaluations with Carnegie Mellon on network-security exploitation, had models undergo pre-deployment testing by both the US and UK AI safety institutes, and built a dedicated partnership with the US Nuclear National Security Administration to evaluate models for nuclear and radiological risk in a classified setting ([Anthropic, 2025](#ev-anthropic-frontier-red-team-2025-external-partners)). You don't need a partnership with a national security agency to take the principle: an internal team checking its own organization's work has limits an outside evaluator doesn't.

## Turn findings into fixes, not just a report

A red-team report that lists vulnerabilities and goes in a drawer accomplished nothing. Route findings through the same sign-off gate your [AI Governance Lead](/ai-accountability/04-ai-governance-lead/index.md) runs for deployment review — a critical finding should be able to block a launch, not just get logged for someday.

## Sources

<!-- generated from validation/evidence.yaml — do not edit; run scripts/build_index.py -->

- **Anthropic — *Strategic Warning for AI Risk — Progress and Insights from our Frontier Red Team*, 2025.** By developing evaluation plans in advance and committing to capability thresholds that would motivate increased levels of security, the work of Anthropic's Frontier Red Team enhances our ability to advance the frontier of AI rapidly. [View source](https://www.anthropic.com/news/strategic-warning-for-ai-risk-progress-and-insights-from-our-frontier-red-team){#ev-anthropic-frontier-red-team-2025-thresholds-methodology} · verified 2026-07-02 · primary
- **Anthropic — *Strategic Warning for AI Risk — Progress and Insights from our Frontier Red Team*, 2025.** In Capture The Flag (CTF) exercises — cybersecurity challenges that involve finding and exploiting software vulnerabilities in a controlled environment — Claude improved from the level of a high schooler to the level of an undergraduate in just one year. [View source](https://www.anthropic.com/news/strategic-warning-for-ai-risk-progress-and-insights-from-our-frontier-red-team){#ev-anthropic-frontier-red-team-2025-cybersecurity-progress} · verified 2026-07-02 · primary
- **Anthropic — *Strategic Warning for AI Risk — Progress and Insights from our Frontier Red Team*, 2025.** a model's ability to discover and exploit vulnerabilities in insecure software [with Carnegie Mellon University]... have undergone pre-deployment testing by both the US AI Safety Institute and UK AI Security Institute... a first-of-its-kind partnership [with NNSA] evaluating models in a classified environment for knowledge relevant to nuclear and radiological risk. [View source](https://www.anthropic.com/news/strategic-warning-for-ai-risk-progress-and-insights-from-our-frontier-red-team){#ev-anthropic-frontier-red-team-2025-external-partners} · verified 2026-07-02 · primary
