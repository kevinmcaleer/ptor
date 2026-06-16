---
layout: ptor
title: "Sc is for Scratch — The Periodic Table of Robotics"
name: Scratch
code: Sc
number: 9
category: code
description: "Snap colourful blocks together and watch your robot come to life — Scratch is where millions of builders write their very first line of code."
cover: /assets/img/ptor/og/sc.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - scratch
  - education
  - beginner
  - block coding
related:
  - mp
  - py
  - mb
  - le
  - ar
external_link: https://scratch.mit.edu
external_label: Scratch (MIT)
---

Everyone starts somewhere. For a huge number of robot builders, that somewhere is a browser tab full of colourful interlocking blocks — and that's a brilliant place to begin.

## What is Scratch?

Scratch is a free, browser-based visual programming language created by MIT. Instead of typing syntax, you drag and snap together blocks that represent actions, loops, conditions, and events. The blocks are colour-coded by category so it's immediately obvious what each one does.

It runs entirely in your browser at [scratch.mit.edu](https://scratch.mit.edu) — nothing to install, no terminal, no error messages about missing semicolons. You build a project, click the green flag, and it runs.

Scratch is aimed at ages 8–16, but plenty of adults use it as a rapid prototyping tool or to teach others. The MIT community hosts millions of shared projects you can remix and learn from.

## Blocks snap into a program

You build a program by stacking blocks top to bottom — each one runs in order, and blocks like **forever** wrap around the ones inside them. Here's that first control loop drawn as the blocks themselves:

```
   ┌────────────────────────────┐
   │ when [green flag] clicked   │
   └────────────────────────────┘
   ┌────────────────────────────┐
   │ forever                     │
   │  ┌───────────────────────┐  │
   │  │ move (10) steps        │  │
   │  └───────────────────────┘  │
   │  ┌───────────────────────┐  │
   │  │ if on edge, bounce     │  │
   │  └───────────────────────┘  │
   └────────────────────────────┘
```

That `forever` loop wrapping a `move` and an `if` is exactly the sense-act loop a real robot runs — you've written a control loop without typing a single semicolon.

## Why robot builders care

Scratch teaches the core ideas of programming — sequences, loops, conditionals, variables, events — in a form where you can't make a syntax error. That means you spend your mental energy on *what you want the robot to do* rather than on where you forgot a closing bracket.

Some robot kits connect directly to Scratch. The **micro:bit** has a Scratch extension that lets you control its LEDs, buttons, and radio from a Scratch project. **LEGO SPIKE** Prime and **LEGO Mindstorms** both have Scratch-derived block environments. The **HP Robots Otto** kit supports a block-based language alongside Python and C++, so you can [start with blocks and graduate to text code](/blog/hprobotsotto.html) on the same hardware.

Block coding also makes a great teaching tool if you want to run a robotics club or show a younger family member how robots think.

## Get started

The fastest first step is to open Scratch in your browser and build something in ten minutes:

1. Go to [scratch.mit.edu](https://scratch.mit.edu) and click **Start Creating** — no account needed.
2. Build a simple loop: drag a **forever** block, drop a **move 10 steps** inside it, add an **if on edge, bounce** block, and click the green flag.
3. You've just written your first control loop — the same concept that steers real robots.

Once blocks start to feel limiting, that's the signal to level up. Python is the natural next step. Kevin's [Python for Beginners](/learn/python/01_intro.html) course picks up exactly where Scratch leaves off, introducing text-based code with the same beginner-friendly pace. From there, [Learn MicroPython — the basics](/learn/micropython/00_intro.html) gets you onto real hardware like the Raspberry Pi Pico.

The road from colourful blocks to a physical robot is shorter than you think. Scratch is just the first satisfying snap.
