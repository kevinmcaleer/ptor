---
layout: ptor
title: "Dc is for DC Motors — The Periodic Table of Robotics"
name: DC Motors
code: Dc
number: 29
category: power
description: "Master DC motors and you can make almost anything move — wheels, tracks, arms, and more — with just a few volts and some code."
cover: /assets/img/ptor/og/dc.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - motors
  - robot
  - power
  - motion
related:
  - hb
  - pw
  - wh
  - sm
  - ba
---

A DC motor is the heartbeat of most beginner robots. Two wires in, voltage applied, shaft spins. It is genuinely that simple — and that satisfying.

## What is a DC Motor?

A DC (Direct Current) motor converts electrical energy into rotational motion. Feed it positive voltage and it spins one way; reverse the polarity and it spins the other way. That reversibility is what lets your robot go both forwards and backwards.

Most small robots use **N20 micro gear motors** or **TT yellow motors**. These come with a built-in gearbox that trades raw speed for torque — so instead of spinning at 10,000 RPM with no grunt, you get a more usable 100–300 RPM that can actually shift a chassis.

Key specs to know:

- **Voltage rating** — typically 3 V to 12 V for hobby motors
- **Stall current** — the current drawn when the motor is held still (can be 5–10× the running current)
- **RPM** — revolutions per minute at rated voltage, with or without the gearbox
- **Torque** — measured in mN·m or kg·cm; bigger numbers mean more pushing power

## Why robot builders care

Wheels need DC motors. Tank tracks need DC motors. Robot arms, conveyor belts, spinning sensors — most of them come back to a DC motor somewhere in the chain.

The real skill is *control*. A motor connected directly to a battery just runs at full speed. To vary the speed you use [PWM](/periodic-table/pw.html) (Pulse Width Modulation) — switching the motor on and off very fast so it averages out to a lower effective voltage. To reverse direction safely you need an [H-bridge](/periodic-table/hb.html), a circuit that lets you flip the current flow without rewiring anything.

That combination — H-bridge for direction, PWM for speed — is what almost every motor driver board gives you in one tidy package.

## Get started

The classic entry point is building a two-wheeled robot and writing code to drive it forwards, backwards, and through a turn. The [MicroPython Robotics Projects with the Raspberry Pi Pico](/learn/micropython_robotics/01_intro.html) course walks you through exactly this: controlling motors from a Pico using MicroPython, reading sensors, and combining it all into an autonomous robot.

If you want to start with Arduino instead, the [Learn how to program SMARS with Arduino](/learn/smars_code/01_lesson_01.html) course covers motor control using a motor shield — a board that stacks onto an Arduino and handles all the H-bridge circuitry for you. SMARS itself uses two N20 gear motors and is a brilliant first build.

A quick experiment to try right now: connect a small DC motor to a battery via a switch. Note the direction. Swap the wires. Watch it reverse. That simple moment is the foundation of every wheeled robot you will ever build — the fun is in understanding *why* it works, and then making it do exactly what you want.
