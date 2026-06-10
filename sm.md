---
layout: ptor
title: "Sm is for SMARS — The Periodic Table of Robotics"
name: SMARS
code: Sm
number: 73
category: robots
description: "The Screwless Modular Assemblable Robotic System: a 3D-printable, beginner-friendly robot you can build, code and customise at home."
cover: /assets/img/ptor/og/sm.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - smars
  - 3d_printing
  - arduino
  - robotics
related:
  - bb
  - pc
  - rv
  - ar
  - pr
external_link: https://www.smarsfan.com
external_label: SMARS Fan Community
---

SMARS is the robot that launched a thousand first builds. If you've ever wanted to go from zero to a moving, coding robot without spending a fortune or hunting down special hardware, this is where you start.

## What is SMARS?

SMARS stands for **Screwless Modular Assemblable Robotic System**. It's a small tracked robot designed to be 3D-printed and held together with snap-fit connections — no screws, no glue, no specialist tools. The original design was created by Kevin McAleer and released as open source, and a whole community has grown around it ever since.

The core robot is compact — around 100mm long — and runs on two DC motors with tank-style tracks. The main board is an Arduino Uno or Nano, making it approachable for beginners. The Pico and Pico W versions (PicoSMARS) bring MicroPython and wireless connectivity into the mix. There are also quad-legged variants, mini versions, and countless community mods.

## Why robot builders care

SMARS ticks nearly every box for a first robot:

- **Printable** — download the STL files, print in PLA, done.
- **Modular** — swap sensor mounts, add new attachments, or remix the chassis entirely.
- **Cheap** — the electronics cost around £15–£20 depending on what you have.
- **Teachable** — the simple two-motor differential drive is a perfect sandbox for learning PID control, obstacle avoidance, line following, and more.
- **Community-backed** — thousands of builders have shared remixes, and the [SMARS Fan](https://www.smarsfan.com) site collects the best of them.

Whether you're using C++ on an Arduino or MicroPython on a Pico W, the hardware stays the same. That means you can focus on learning to code rather than fighting the build.

## Get started

The best place to begin is the full **[SMARS course](/learn/smars/00_intro.html)** — it walks you through printing the parts, wiring up the motors, and getting your first code running. Once you've got it moving, the **[Learn to program SMARS with Arduino](/learn/smars_code/01_lesson_01.html)** course takes you step by step through writing proper robot code.

Want to design your own SMARS variant? The **[Build a SMARS Robot in Fusion 360](/learn/smars_fusion360/00_intro.html)** course shows you how to model new parts from scratch.

If you want to swap the Arduino for a Raspberry Pi Pico W and write MicroPython, check out the [PicoSMARS 2](/blog/picosmars.html) project — it adds WiFi to the mix and opens up all sorts of remote-control possibilities.

SMARS is proof that you don't need a big budget or a workshop full of gear to build something genuinely capable. Print the parts, snap it together, and start coding. That first time the tracks spin under your own code is a moment you won't forget.
