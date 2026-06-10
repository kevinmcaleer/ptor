---
layout: ptor
title: "Bb is for BurgerBot — The Periodic Table of Robotics"
name: BurgerBot
code: Bb
number: 74
category: robots
description: "A beginner-friendly 3D-printed round robot powered by Raspberry Pi Pico — proof that great robots come in small, stackable packages."
cover: /assets/img/ptor/og/bb.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - burgerbot
  - robot
  - pico
  - micropython
  - 3d_printing
related:
  - sm
  - pi
  - pr
  - mp
  - dw
---

BurgerBot is a compact, circular robot you can print at home, wire up in an afternoon, and be driving around the kitchen by teatime. It's one of the friendliest first robot projects out there.

## What is BurgerBot?

BurgerBot is a two-wheeled differential-drive robot shaped like — yes — a burger. The body is entirely 3D printed. Inside sits a Raspberry Pi Pico (or Pico W), a pair of micro metal motors, a Motor SHIM from Pimoroni, a LiPo battery, and an ultrasonic distance sensor on the front. That's it. The whole build costs well under £30 in parts, and the print time is just a few hours.

The robot has gone through several versions. V1 drives around and avoids obstacles. V2 adds a pen holder so BurgerBot can draw patterns — a brilliant introduction to turtle-style Logo programming. V3 gains a custom PCB that tidies up all the wiring and makes the build even cleaner.

Key specs for the standard build:
- **Microcontroller:** Raspberry Pi Pico / Pico W
- **Motors:** 2× micro metal motors with moon-buggy wheels
- **Sensor:** 3.3 V ultrasonic rangefinder (front-mounted)
- **Power:** Galleon LiPo via Pimoroni LiPo SHIM
- **Code:** MicroPython

## Why robot builders care

BurgerBot is a masterclass in "just enough". It has everything you need to learn the fundamentals — motor control, sensor reading, simple autonomy — without drowning you in complexity before you've started. Because the chassis is 3D printed, you can modify it: add a servo arm, swap the sensor, redesign the top plate. It's also Bluetooth-capable on the Pico W variant, so remote control is only a few lines of MicroPython away.

The pen-drawing version is especially powerful for teaching. Watching a robot you built trace out a square or a spiral makes abstract programming concepts — loops, angles, functions — instantly concrete.

## Get started

Start with the full build guide: [Build your own BurgerBot](/learn/burgerbot/00_intro.html). It walks you through printing, wiring, and writing your first MicroPython program step by step.

Once you're driving around, check out [BurgerBot V2 — Quick on the Draw](/blog/burgerbot_v2.html) to add a pen holder and teach your robot to sketch. When you're ready to level up the hardware, [Making a Custom PCB for BurgerBot](/blog/burgerbot-pcb.html) shows how to design a proper PCB that replaces all the breakout boards.

Want wireless control? [Gamepad & BurgerBot](/blog/gamepad-burgerbot.html) walks you through building a Bluetooth gamepad remote from scratch using a second Pico.

Your first task: download the STL files, start the print, and order the Pimoroni parts. By the time the print finishes, the components will almost be on their way.
