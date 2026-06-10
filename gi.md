---
layout: ptor
title: "Gi is for Git — The Periodic Table of Robotics"
name: Git
code: Gi
number: 14
category: code
description: "Track every change to your robot's code, roll back mistakes instantly, and collaborate with the world — Git is the essential safety net for any project."
cover: /assets/img/ptor/og/gi.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - git
  - software
  - version control
  - github
related:
  - li
  - do
  - py
  - os
  - mp
external_link: https://git-scm.com
external_label: git-scm.com
---

Every robot project grows. What starts as a single script turns into dozens of files, tweaks, experiments, and "I wonder what happens if I change this" moments. Git is how you keep track of all of it without losing your mind.

## What is Git?

Git is a version control system — a tool that records a full history of every change you make to your project files. Each time you save a snapshot (called a *commit*), Git stores exactly what changed, when, and why. You can scroll back through that history at any time, compare two versions side by side, or restore a file you accidentally broke.

Git was created by Linus Torvalds in 2005 — the same person who wrote the Linux kernel — and it's free, open source, and everywhere.

A few key ideas to know:

- **Repository (repo)** — a folder whose entire history Git is tracking.
- **Commit** — a saved snapshot with a short message describing what changed.
- **Branch** — a separate line of development, so you can try things out without touching the main working code.

## Why robot builders care

When you're tuning a PID loop or rewriting your motor control code, things break. Without Git, a bad experiment can overwrite perfectly working code and you're left guessing what you changed. With Git, you just run `git checkout` and the broken version disappears.

Git also means you can share your designs with the community. Almost every open-source robot platform — SMARS, ROS packages, MicroPython libraries — lives in a Git repository. Knowing Git means you can clone those projects, contribute fixes, and share your own builds with the world.

## Get started

The best place to begin is the command line — on Raspberry Pi OS, Git is already installed.

The [Introduction to the Linux Command Line on Raspberry Pi OS](/learn/linux_intro/01_intro_terminal.html) course on this site walks you through everything from basic terminal use up to [Introduction to Git](/learn/linux_intro/14_intro_git.html) and [Basic Git Commands](/learn/linux_intro/15_basic_git_commands.html) — a natural progression that puts Git in context alongside the other tools you'll use every day.

Here's the mini-project that makes Git click: create a new folder for a robot project, run `git init` inside it, write a short Python script, then commit it with `git commit -m "first working motor test"`. Change one line, commit again. Run `git log` to see your history, then `git diff` to see exactly what you changed. That two-minute exercise teaches you more about Git than any amount of reading.

Once you're comfortable with local commits, create a free account on GitHub and push your repo there. Now your code is backed up and visible to the whole maker community — a big deal when you've spent a weekend building something cool.

A tidy Git history also makes debugging easier. If your robot worked two weeks ago and doesn't now, `git bisect` can find the exact commit that broke it — a time machine for your code.
