---
layout: ptor
title: "Br is for Breadboard — The Periodic Table of Robotics"
name: Breadboard
code: Br
number: 11
category: foundations
description: "The breadboard is your best friend in the workshop — prototype any circuit in minutes, no soldering, no fuss, no permanent mistakes."
cover: /assets/img/ptor/og/br.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - prototyping
  - circuits
related:
  - so
  - re
  - io
  - el
  - ci
external_link: https://en.wikipedia.org/wiki/Breadboard
external_label: What is a Breadboard?
---

Every great robot starts with a few jumper wires poking into a white plastic grid. The breadboard is where ideas become reality — fast, cheap, and completely reversible.

## What is a Breadboard?

A breadboard is a reusable prototyping board that lets you build electronic circuits without any soldering. Components and wires push into a grid of spring-loaded holes. Rows are connected internally, so anything you plug into the same row shares a connection.

The two long rails running down each side carry power (usually 3.3 V or 5 V) and ground. The central area is split in two, with rows of five holes either side of a central dividing channel — perfect for straddling an IC chip across the gap.

A full-size breadboard has 830 tie points. Mini breadboards (170 tie points) are compact enough to sit right next to a Raspberry Pi Pico.

## How the holes connect

This is the one thing worth burning into memory: the **power rails** run the *length* of the board, while the **terminal strips** in the middle connect in short *vertical* groups of five, broken by the central channel. Lines below show which holes are joined together:

```
   + ═══════════════════════════════  ← red rail  (e.g. 3.3 V), all joined
   − ═══════════════════════════════  ← blue rail (GND), all joined

     a  b  c  d  e        f  g  h  i  j
   1 ●──●──●──●──●        ●──●──●──●──●   each column a–e is one
   2 ●──●──●──●──●        ●──●──●──●──●   net; f–j is a separate
   3 ●──●──●──●──●        ●──●──●──●──●   net. The gap in the
   4 ●──●──●──●──●        ●──●──●──●──●   middle is the channel
   5 ●──●──●──●──●        ●──●──●──●──●   an IC straddles.
            ↑                  ↑
       a–e joined         f–j joined
       (same column)      (same column)
```

Plug two component legs into the same column (say `1a` and `1c`) and they're electrically connected. Span the central channel and the two halves stay separate — which is exactly why a chip's left and right pins don't short together.

## Why robot builders care

Breadboards belong on every maker's workbench, at every skill level. Here is why:

- **Nothing is permanent.** Wired it wrong? Pull it out and try again. No heat gun, no desoldering wick.
- **Fast iteration.** You can test a motor driver circuit in five minutes. If it works, *then* you commit it to solder.
- **Safe for beginners.** Short circuits and wiring mistakes are sorted in seconds, not minutes.
- **Works with everything.** Arduino, Raspberry Pi Pico, ESP32, sensors, LEDs, resistors — if it has legs, it fits a breadboard.

Almost every circuit you see in a robotics tutorial starts its life on a breadboard. Understanding how the rows and columns connect is the single most useful thing you can learn before you touch a soldering iron.

## Get started

Grab a breadboard, a handful of jumper wires, an LED, and a 220-ohm resistor. Connect the LED's long leg (anode) to a GPIO pin via the resistor, and the short leg (cathode) to ground. That's the classic "blink" circuit — and it's the foundation of nearly every robot sensor and actuator you will ever build.

Once you are comfortable, try building a simple sensor circuit: the [Hacky Temperature and Humidity Sensor](/blog/hacky-sensor.html) project is a great first step that puts a breadboard and a Raspberry Pi Pico to work together. The [Chicken Nugget Piano](/blog/chicken-nugget-piano.html) is another fun one — a touch-sensor project that shows just how quickly you can test wild ideas on a breadboard.

When you want to go deeper on working with GPIO pins alongside your circuits, the [Raspberry Pi Pico with MicroPython — GPIO Mastery](/learn/micropython_gpio/00_intro.html) course takes you from a blinking LED all the way to real-world sensor projects.

The golden rule: breadboard first, solder later. Once a circuit has survived a week on the breadboard without issues, it has earned its place on a proper PCB.
