---
layout: ptor
title: "Hb is for H-Bridge — The Periodic Table of Robotics"
name: H-Bridge
code: Hb
number: 46
category: power
description: "Four clever switches let you flip a motor's direction on demand — the circuit that turns a microcontroller into a proper robot driver."
cover: /assets/img/ptor/og/hb.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - motors
  - electronics
  - dc motors
  - motor driver
related:
  - dc
  - tr
  - pw
  - io
  - mp
---

Without an H-bridge, your motor only ever spins one way. With one, you get full control — forward, backward, stop, and everything in between.

## What is an H-Bridge?

An H-bridge is a circuit made from four switches (usually transistors or MOSFETs) arranged in an "H" shape, with the motor sitting across the middle bar. By opening and closing pairs of switches, you reverse the direction of current through the motor — and that reverses the spin.

The two most common ICs you'll meet on a maker's bench are the **L298N** and the **DRV8833**. The L298N is a chunky dual H-bridge that handles up to 2 A per channel and works with motors up to around 35 V — great for the heavier plastic-geared motors inside a SMARS or BurgerBot. The DRV8833 is a more modern, lower-voltage option (up to 10 V, 1.5 A per channel) with better efficiency and a smaller footprint.

Both chips contain *two* H-bridges, so a single IC controls both motors on a two-wheeled robot.

The logic is beautifully simple:

| IN1 | IN2 | Motor |
|-----|-----|-------|
| HIGH | LOW | Forward |
| LOW | HIGH | Backward |
| Same | Same | Brake / coast |

Add PWM on the enable pin and you also control speed.

## Why robot builders care

Every wheeled or tracked robot needs to go both ways. A microcontroller GPIO pin can source maybe 8–16 mA — nowhere near enough to drive a DC motor directly, and it can't reverse current at all. The H-bridge solves both problems: it amplifies the tiny GPIO signal into amps of motor current, and the four-switch topology lets you flip polarity instantly.

Tank-steering robots (SMARS, most line-followers, rover designs) use two independent H-bridge channels — one per side. Speed up one side while slowing the other and you steer. Reverse one side and you spin on the spot.

## Get started

The fastest route from zero to spinning motors is the [MicroPython Robotics course](/learn/micropython_robotics/01_intro.html), which has a dedicated lesson on wiring an L298N to a Raspberry Pi Pico and writing clean forward/backward/turn functions in MicroPython. If you prefer Arduino and C++, the [SMARS build and code guide](/blog/smars.html) walks you through the Fundumoto motor shield — itself a pre-built dual H-bridge that plugs straight onto an Arduino Uno.

A good first experiment: wire up a single DC motor to an L298N and a Pico, then write four one-line functions — `forward()`, `backward()`, `left()`, `right()` — each setting IN1 and IN2 high or low. Once that clicks, adding a second motor and stitching those four functions together is all it takes to have a robot that actually drives.
