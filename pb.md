---
layout: ptor
title: "Pb is for PCB Design — The Periodic Table of Robotics"
name: PCB Design
code: Pb
number: 38
category: foundations
description: "Turn your tangled breadboard into a clean, professional printed circuit board you can order online for just a few pounds."
cover: /assets/img/ptor/og/pb.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - pcb
  - electronics
  - kicad
  - circuits
related:
  - el
  - ci
  - so
  - tr
  - br
external_link: https://www.kicad.org
external_label: KiCad
---

You've got a working prototype on the breadboard. Wires everywhere, a few jumpers that fall out if you sneeze. A custom PCB fixes all of that — and it makes your robot look seriously good.

## What is PCB Design?

PCB stands for Printed Circuit Board. Instead of loose wires connecting components, you design copper tracks etched onto a board that do the job permanently and reliably. You place every component on a digital canvas, route the connections between them, and then send a set of files (called Gerbers) to a manufacturer. A few days later, real boards turn up at your door.

Modern PCB design tools are free and surprisingly accessible. **KiCad** is the most popular open-source option and runs on Windows, Mac, and Linux. **EasyEDA** is browser-based and directly linked to JLCPCB's fab service, so you can go from schematic to order in one afternoon. Most hobbyist fabs charge around £5–£10 for five boards — it's genuinely cheap.

A two-layer board (top and bottom copper) is enough for almost every robot project. You place components like resistors, microcontrollers, motor drivers, and connectors on the schematic first, then move to the layout view to arrange them physically and draw the copper traces.

## Why robot builders care

A custom PCB transforms a one-off prototype into something repeatable. You can build five identical robots without re-wiring each one. Connections are solid — no breadboard slop, no jumper pin wiggling loose mid-run. You can also add mounting holes that line up exactly with your chassis, integrate status LEDs, and expose only the connectors you actually need.

It also makes debugging easier. If something breaks, you know exactly where each track runs. There are no mystery wires to trace.

For robots with tight space constraints — a small wheeled bot, a wearable, or a legged robot — fitting a custom PCB rather than a nest of breadboard wires can save significant space and weight.

## Get started

The fastest route in is to take a project you've already built on a breadboard and recreate it in KiCad. Open the schematic editor, place your components, wire them up, then switch to the PCB layout and route the traces. Aim for a board no bigger than 50 × 50 mm for your first attempt — that's often the minimum size tier for free or near-free pricing at fab houses.

Kevin has walked through exactly this process for a couple of projects on the site. The [BurgerBot custom PCB](/blog/burgerbot-pcb.html) article shows the whole workflow from idea to ordering, and the [Bluetooth Remote Control custom PCB](/blog/bluetooth-remote-pcb.html) covers designing a gamepad-style controller board around the Raspberry Pi Pico W. Both are great reference points when you're starting out.

Once your board arrives, pair it with a good soldering session (see the **So** — Soldering element) and you'll have a robot you'd be proud to show off.
