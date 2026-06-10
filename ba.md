---
layout: ptor
title: "Ba is for Batteries — The Periodic Table of Robotics"
name: Batteries
code: Ba
number: 28
category: power
description: "Choose the right battery and your robot roams free — get the chemistry wrong and it dies mid-demo."
cover: /assets/img/ptor/og/ba.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - power
  - hardware
related:
  - dc
  - sv
  - pw
  - oh
  - el
---

No battery, no robot. It really is that simple.

The moment you cut the cable and run on battery power, your robot goes from a desk ornament to something that can actually explore the world — and choosing the right cell makes the difference between a robot that lasts all day and one that gives up after five minutes.

## What is a Battery?

A battery is an electrochemical device that stores energy and releases it as electricity. For robot builders, the three types you'll encounter most are:

- **Alkaline AA/AAA** — cheap and easy to buy, but voltage drops as they discharge, and they can't deliver big current spikes without sagging. Fine for low-power prototypes.
- **NiMH rechargeables** — a better choice than alkalines for most beginner robots. Reusable, reasonably cheap, and they handle motor loads well.
- **LiPo (Lithium Polymer)** — the favourite for RC cars, drones, and performance robots. High energy density, flat discharge curve, and they can push serious current. Rated in milliamp-hours (mAh) and cell count (1S = 3.7 V, 2S = 7.4 V, etc.). Handle them carefully — they don't like being over-discharged or punctured.
- **18650 Li-ion cells** — the same chemistry as LiPo, but in a sturdy cylindrical can. Used in power banks and many off-the-shelf battery packs. Great for Raspberry Pi robots.

A useful rule of thumb: **capacity (mAh) tells you how long; voltage tells your motors how fast**.

## Why Robot Builders Care

Every component in your robot — microcontroller, motors, servos, sensors — draws current. Motors are the hungry ones. A stall current spike from a pair of DC motors can be five to ten times the running current, so a battery that looks adequate on paper can sag into a low-voltage reset at exactly the wrong moment.

You also need to match voltage to your system. A Raspberry Pi wants a stable 5 V; a motor driver might want 6–12 V. Often you'll run two separate supplies, or use a buck converter to step voltage down from a single higher-voltage LiPo pack.

Wrong battery choice is behind a surprising number of "my robot acts weird" moments.

## Get Started

The best starting point is to understand your options properly. Kevin's deep-dive post [Power up your robot projects](/blog/power.html) walks through alkaline, NiMH, LiPo, solar, and even wireless charging.

Once you're ready to put that knowledge into practice, the [SMARS course](/learn/smars/00_intro.html) shows you how a complete battery-powered wheeled robot fits together from scratch — including how the power wiring works.

For a broader picture of how batteries slot into the electronics of a full build, [Robotics 101](/learn/robotics_101/00_overview.html) covers the fundamentals that underpin every robot you'll ever make.

A good first experiment: take any robot you've built, swap out plain alkalines for NiMH rechargeables, and notice how much more consistently the motors run. Then try a small LiPo pack (with the right protection circuit) and see what changes. Your robot will thank you.
