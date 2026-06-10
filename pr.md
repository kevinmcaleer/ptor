---
layout: ptor
title: "Pr is for 3D Printing — The Periodic Table of Robotics"
name: 3D Printing
code: Pr
number: 57
category: making
description: "Turn digital designs into real robot parts overnight — 3D printing is the workshop superpower every maker needs in their toolkit."
cover: /assets/img/ptor/og/pr.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - 3d_printing
  - 3dprinting
  - making
  - fabrication
related:
  - cd
  - fc
  - fu
  - ch
  - sm
external_link: https://www.printables.com
external_label: Printables
---

You design a robot chassis at midnight. By morning, it's sitting on your desk. That's the magic of 3D printing — it collapses the gap between idea and object.

## What is 3D Printing?

3D printing (also called additive manufacturing) builds physical objects layer by layer from a digital file. The most common type for robot builders is **FDM** (Fused Deposition Modelling) — a heated nozzle melts plastic filament and deposits it in precise paths until your part takes shape.

The two filaments you'll reach for most often are:

- **PLA** — easy to print, rigid, great for prototypes and lightweight parts
- **PETG** — tougher, slightly flexible, better for parts that take knocks or need some give

A typical desktop FDM printer has a build volume around 220 × 220 × 250 mm and a layer height of 0.2 mm. That's more than enough for most robot chassis, brackets, mounts, and enclosures.

## Why robot builders care

Almost every custom robot you see on kevsrobots.com has 3D printed parts in it. Brackets rarely come off the shelf in the right shape. Motor mounts need to be exactly the right distance apart. Servo horn extensions have to fit your specific design.

3D printing lets you iterate fast. Print a bracket, test the fit, tweak the CAD file, print again. You can go through four or five design revisions in a day without spending a penny on new hardware. It also means you can share your designs freely — publish the STL files and anyone in the world can build exactly what you built.

Robots that simply wouldn't be possible without 3D printing: quadrupeds, hexapods, custom rover frames, robot arms, and tiny chassis like SMARS. The parts are too complex and too specific to buy off the shelf.

## Get started

If you're new to 3D printing for robots, start by printing something someone else has already designed. Download a free STL from [Printables](https://www.printables.com) or [Thingiverse](https://www.thingiverse.com), slice it in PrusaSlicer or Cura (both free), and hit print. Get comfortable with your machine before you start designing.

When you're ready to design your own parts, FreeCAD is a brilliant free starting point — the [Introduction to FreeCAD for Beginners](/learn/freecad/01_introduction_to_freecad.html) course will walk you through it step by step. Once you want to design a complete printable robot from the ground up, the [Building SMARS with FreeCAD](/learn/freecad_smars/00_intro.html) course shows you exactly that workflow.

Want to see what a fully 3D-printed robot looks like in practice? [BurgerBot](/blog/burgerbot.html) is a cracking example — every structural part is printed, and the whole thing is designed to be accessible to beginners.

The learning curve is real, but it's worth every hour. Once you can print your own parts, you stop being limited by what's available to buy. You become the manufacturer.
