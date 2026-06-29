---
type: Playbook
title: Get a Step-by-Step How-To
description: Turn a vague goal into clear, ordered steps.
tags: [how-to, explaining]
timestamp: "2026-06-24"
---

## When to use this

You know what you want to accomplish, but not how to get there. You want a clear, ordered action plan you can actually follow, not a general overview.

## The prompt

```
You are a clear, practical guide who gives step-by-step instructions.

Goal: [WHAT I WANT TO DO — be specific]

My situation: [e.g. "I've never done this before", "I've tried once and got stuck at X", "I'm doing this on a Mac", "I have about 30 minutes"]

Give me numbered steps, in the order I should do them. For each step, tell me exactly what to do and flag anything I should watch out for. If there are things I'll need before I start, list those first.
```

## Before and after

**Before:** The reader wants to set up automatic backups for their laptop but has no idea where to start.

**After (excerpt):**

> **What you'll need first:**
> - An external hard drive with at least as much space as your laptop's storage
>
> **Steps:**
> 1. Plug in your external hard drive.
> 2. On a Mac: go to System Settings → General → Time Machine. On Windows: go to Settings → System → Backup.
> 3. Select "Add Backup Disk" (Mac) or "Add a drive" (Windows), then choose your external drive.
> 4. Turn on automatic backups. The first backup will take a while — leave your computer plugged in.
>
> ⚠️ Don't unplug the drive mid-backup or you may corrupt the backup file.

## Make it yours

- Add `"Assume I have no prior experience"` if you're starting from zero. Or add `"Skip the basics — I know how to [X]"` to fast-forward past steps you already know.
- Ask for time estimates: `"Include roughly how long each step takes"`.
- Request a simpler path: `"Is there a faster or easier way to do this?"`.
- Ask what can go wrong: `"After the steps, add a short troubleshooting section for the most common problems"`.

## Watch out for

AI works best for common, well-documented tasks. For niche software, very recent changes, or anything requiring exact version-specific steps, double-check the official documentation. The AI may give you instructions that are close but slightly out of date.
