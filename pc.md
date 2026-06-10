---
layout: ptor
title: "Pc is for PicoCat — The Periodic Table of Robotics"
name: PicoCat
code: Pc
number: 75
category: robots
description: "A 3D-printable, open-source robot cat powered by the Raspberry Pi Pico — 12 servos, MicroPython, and a whole lot of feline personality."
cover: /assets/img/ptor/og/pc.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - picocat
  - pets
  - micropython
  - servos
  - 3d_printing
related:
  - sm
  - sv
  - mp
  - ik
  - pr
external_link: https://github.com/kevinmcaleer/picocat
external_label: PicoCat on GitHub
---

PicoCat is a quadruped robot cat you can 3D print, wire up with servos, and program in MicroPython — all on a Raspberry Pi Pico. It is friendly, surprisingly expressive, and a brilliant way to get hands-on with legged robots.

## What is PicoCat?

PicoCat is an open-source, 3D-printable robot cat originally inspired by the OpenCat project from Dr Rongzhong Li. Kevin McAleer remixed the design specifically for the Raspberry Pi RP2040 chip, making it cheaper and easier to build with parts most makers already know.

The robot has **12 servo motors** — three per leg — giving it a full range of leg movement. You can make it walk, trot, stretch, and even wag its tail. The brain is either a **Raspberry Pi Pico** paired with a PCA9685 servo driver, or a **Pimoroni Servo 2040** board, which combines the RP2040 and 18-channel servo control into one tidy package.

Body parts are all 3D printed and the code is written in **MicroPython**, so the barrier to entry is genuinely low. If you can print parts and solder a few connectors, you can build one.

## Why robot builders care

Legged robots are a big step up from wheeled ones. You move from spinning motors to coordinating multiple servos in precisely timed sequences — that's a proper introduction to **gait programming** and the early stages of **inverse kinematics**.

PicoCat puts all of that within reach:

- **Affordable** — a Pico, a servo driver, 12 small servos, and some PLA filament gets you most of the way there.
- **Open source** — STL files and MicroPython code are freely available on GitHub.
- **Extendable** — the Servo 2040 board leaves spare servo channels for extras like a head, a tail, or sensors.
- **A stepping stone** — once you understand how PicoCat walks, hexapods and full humanoids start to make a lot more sense.

It is also just very satisfying to watch. Something about a small cat robot trotting across a desk brings genuine joy to a room.

## Get started

Start with the **[PicoCat v2 project page](/blog/picocat-v2.html)** — it covers the hardware changes in version 2, the switch to the Servo 2040 board, and what the updated MicroPython code looks like. Then head to the **[PicoCat Lives build log](/blog/picocat-lives.html)** for a full gallery of the printed parts and download links for the STL files.

Once you have the hardware sorted, the **[MicroPython Robotics Projects with the Raspberry Pi Pico](/learn/micropython_robotics/01_intro.html)** course is a great companion — it covers motor and servo control in MicroPython in a structured, beginner-friendly way.

For the curious: PicoCat has also been remixed into **Bugs the Robo-Bunny**, swapping the cat body for bunny ears and a seasonal look. Same electronics, same code, very different vibe. That is the beauty of an open-source design — once you understand the platform, you can take it anywhere.
