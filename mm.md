---
layout: ptor
title: "Mm is for Multimeter — The Periodic Table of Robotics"
name: Multimeter
code: Mm
number: 55
category: foundations
description: "The first tool you grab when a circuit misbehaves — a multimeter reads voltage, current, and resistance in seconds."
cover: /assets/img/ptor/og/mm.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - tips
  - debugging
  - tools
related:
  - oh
  - re
  - so
  - br
  - to
---

When nothing works and you don't know why, a multimeter is the answer. It's a small handheld device that tells you what electricity is actually doing — not what you think it should be doing.

## What is a Multimeter?

A multimeter measures three fundamental electrical quantities:

- **Voltage (V)** — the electrical potential between two points
- **Current (A)** — how much charge is flowing
- **Resistance (Ω)** — how much a component opposes current flow

Most meters also include a **continuity mode** that beeps when two points are connected, and a **diode test** mode. Budget multimeters start at around £8–£15 and are perfectly capable for hobby robotics.

## Why robot builders care

Robots are full of things that can go wrong electrically. A motor that won't spin might have a dead battery, a broken wire, a blown fuse, or a fried motor driver — all of which look identical to the naked eye. A multimeter cuts through the guesswork.

Here's how you'll use it constantly:

- **Checking battery voltage** — a "fully charged" Li-ion should read ~4.2 V per cell. If it shows 3.5 V or less, the robot won't behave normally.
- **Verifying a power rail** — probe your 3.3 V or 5 V pin to confirm the regulator is actually outputting what you expect.
- **Testing continuity** — drag the probes along a wire to find the break, or confirm your solder joints are solid.
- **Fault-finding sensors** — an ultrasonic or IR sensor that "doesn't work" is often just wired to the wrong pin. Probe the output and watch the number change as you move your hand in front of it.

Without a multimeter, debugging electronics means guessing. With one, you know.

## Get started

If you don't own a multimeter yet, buy one before you buy almost anything else. The [10 tips for getting started with robotics](/blog/10-tips-for-getting-started-with-robotics.html) post calls out soldering and a multimeter as essential skills for building any robot — and that advice holds up.

Once you have one, practise these three things:

1. **Measure a AA battery** — set the dial to DC voltage (look for V with a straight line), touch the red probe to the positive terminal and the black probe to the negative. A healthy battery reads ~1.5 V.
2. **Test continuity on a known wire** — set the dial to the continuity symbol (often a speaker or diode symbol), touch both ends of a wire. It should beep.
3. **Measure a resistor** — set to resistance (Ω), probe both legs of a resistor from your kit and compare the reading to the colour code.

After that, try checking the power rails on a Raspberry Pi Pico or testing a reed switch in your next project — the [reed switches guide](/blog/reed-switches.html) walks through exactly that kind of hands-on verification step.

For deeper electronics context, the [Robotics 101](/learn/robotics_101/00_overview.html) course covers the fundamentals you'll be measuring with your new favourite tool.
