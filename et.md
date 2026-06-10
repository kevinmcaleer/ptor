---
layout: ptor
title: "Et is for Robot Ethics — The Periodic Table of Robotics"
name: Robot Ethics
code: Et
number: 72
category: intelligence
description: "Who's responsible when your robot gets it wrong? Explore the questions every builder should ask before deploying autonomous machines."
cover: /assets/img/ptor/og/et.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - ai
  - robotics
  - machine learning
  - autonomy
related:
  - ai
  - au
  - ml
  - lm
  - nn
---

The moment your robot can act without a human telling it what to do, the question of *should it* becomes just as important as *can it*.

## What is Robot Ethics?

Robot ethics is the study of the moral questions raised by designing, building, and deploying robots — particularly autonomous ones. It covers things like:

- **Safety** — how do you ensure a robot can't harm a person, even in edge cases?
- **Bias** — if a machine learning model was trained on skewed data, will the robot treat people unfairly?
- **Accountability** — when an autonomous system causes damage, who is responsible: the builder, the manufacturer, the user?
- **Privacy** — a robot with a camera and a microphone is a surveillance device. What data does it collect, and where does it go?
- **Autonomy vs. control** — how much decision-making power should a robot have, and when should a human always remain in the loop?

These aren't abstract philosophy questions. They're engineering decisions that real builders make right now.

## Why robot builders care

You might be building a small rover for your living room, not a military drone — but the principles scale down just as well as they scale up. A few real examples:

- A delivery robot on a pavement has to decide how to navigate around a child or an elderly person — that's an ethics question baked into a pathfinding algorithm.
- A face-recognising pet robot raises privacy questions the moment it stores images of people who didn't consent.
- A combat robot (yes, even in a school competition) needs clear rules about what it can and can't do outside the arena.

Isaac Asimov's Three Laws of Robotics — first published in 1942 — were a brilliant thought experiment, but they have real gaps when you try to apply them to actual code. Read the deep dive on the site: [The Three Laws of Robotics](/blog/three-laws-of-robotics.html) unpacks why they're a useful starting point and where they break down.

Understanding the history of robotics also helps here. The [Robotics 101](/learn/robotics_101/00_overview.html) course covers how our relationship with robots has changed over the decades — which gives useful context for why these ethical questions have become urgent now.

## Get started

You don't need a philosophy degree. Start with one honest question about a project you're already building:

> **"What's the worst thing this robot could do, and have I made that impossible — or just unlikely?"**

Write down your answer. If the answer is "unlikely", work on making it impossible. Add a hardware kill switch. Cap motor speeds. Log every decision your autonomous code makes so you can audit it later. Design for failure.

Then read up. The field of AI ethics is moving fast. Organisations like the [IEEE](https://ethicsinaction.ieee.org/) publish practical guidelines for autonomous systems that are worth bookmarking.

Building responsibly isn't a constraint on creativity — it's what separates a robot you'd be proud to show off from one you'd be embarrassed to explain.
