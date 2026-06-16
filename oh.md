---
layout: ptor
title: "Oh is for Ohm's Law — The Periodic Table of Robotics"
name: "Ohm's Law"
code: Oh
number: 1
category: foundations
description: "V = I × R: the single equation that explains why your LED blew up, your motor stalled, and your battery drained overnight."
cover: /assets/img/ptor/og/oh.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - resistors
  - circuits
related:
  - el
  - re
  - ci
  - ba
  - tr
external_link: https://en.wikipedia.org/wiki/Ohm%27s_law
external_label: Ohm's Law (Wikipedia)
---

Three letters. One equation. A lifetime of usefulness. **V = I × R** is the bedrock that every robot builder eventually meets — usually right after something smells funny.

## What is Ohm's Law?

Ohm's Law describes the relationship between three electrical quantities:

- **V** — Voltage (volts, V): the "pressure" pushing electricity around a circuit
- **I** — Current (amperes, A): the amount of charge actually flowing
- **R** — Resistance (ohms, Ω): how much the circuit opposes that flow

Rearrange it three ways and you can find any one value if you know the other two:

| You want | Formula |
|----------|---------|
| Voltage  | V = I × R |
| Current  | I = V ÷ R |
| Resistance | R = V ÷ I |

That's it. No calculus. No magic. Just multiply or divide.

A 5 V supply pushing current through a 220 Ω resistor produces roughly 23 mA of current — just right to light an LED without burning it out. Swap in a 100 Ω resistor by mistake and you get 50 mA. The LED pops. Ohm's Law would have warned you.

## The Ohm's Law triangle

The fastest way to remember all three forms is the magic triangle. Cover the value you want with your thumb, and the layout of the other two tells you whether to multiply or divide:

```
        ┌───────────┐
        │     V     │     Cover V  →  I × R
        │  ───────  │     Cover I  →  V ÷ R
        │   I  │  R │     Cover R  →  V ÷ I
        └───────────┘

   V = Voltage (volts)
   I = Current (amps)
   R = Resistance (ohms)
```

Side by side (V on top, I and R underneath) means multiply. One value stacked over another (a fraction bar between them) means divide.

## Why robot builders care

Robotics mixes power electronics with delicate logic. You're constantly asking questions like:

- "What resistor do I need in series with this LED?" (use R = V ÷ I)
- "Will this motor pull too much current and brown out my Pi?" (measure R, calculate I)
- "How long will my battery last?" (current draw times capacity)
- "Why is my voltage dropping under load?" (internal resistance of the battery, same law)

Even when you're writing Python or tweaking a servo, the electricity underneath obeys Ohm's Law without exception. Understanding it turns mysterious smoke events into predictable, preventable ones.

## Get started

The best way to internalise Ohm's Law is to measure it yourself. Grab a multimeter, a 9 V battery, and a handful of resistors. Predict the current for each resistor value, then clip your multimeter in series and check. Five minutes of this and it sticks for good.

When you're ready to go further, Kevin's [Robotics 101 course](/learn/robotics_101/00_overview.html) covers Voltage, Current and Resistance in its foundations lessons — a solid grounding before you wire up your first robot. The [Power up your robot projects](/blog/power.html) post is also worth reading: it shows how Ohm's Law applies when you're choosing batteries, regulators and level shifters for a real build.

One practical mini-project: wire an LED to a Raspberry Pi Pico GPIO pin (3.3 V output), calculate the correct current-limiting resistor using R = V ÷ I (aim for 10–20 mA), and light it up. Congratulations — you've just applied Ohm's Law in a real robot component.
