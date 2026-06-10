---
layout: ptor
title: "Lc is for Laser Cutting — The Periodic Table of Robotics"
name: Laser Cutting
code: Lc
number: 61
category: making
description: "Cut precision robot parts from flat sheets of wood or acrylic in seconds — laser cutting turns your SVG designs into real, repeatable components."
cover: /assets/img/ptor/og/lc.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - lasercutting
  - laser_cutting
  - making
  - fabrication
related:
  - cd
  - pr
  - ch
  - pb
  - fc
external_link: https://lightburnsoftware.com
external_label: LightBurn
---

Point a focused beam of light at a sheet of plywood and watch it cut clean, repeatable parts in seconds. Laser cutting is one of the fastest ways to go from a design on screen to a physical robot chassis in your hands.

## What is Laser Cutting?

A laser cutter moves a high-powered laser beam across a flat sheet of material — wood, acrylic, cardboard, MDF, leather — either cutting all the way through or engraving a surface pattern. The two main types you'll encounter as a maker are:

- **Diode lasers** — affordable desktop units (5 W to 40 W) like the Creality Falcon. Great for plywood, MDF, and thin acrylic.
- **CO₂ lasers** — more powerful, typically found in makerspaces, cut thicker acrylic and a wider range of materials cleanly.

You design your parts as vector files (SVG or DXF), set the laser's speed and power, and the machine does the rest. Once the design is right, you can cut identical parts again and again — brilliant for modular or flat-pack robot kits.

Watch out for **kerf** — the sliver of material the laser removes along the cut line. For tight-fitting joints, offset your design by about 0.1–0.2 mm depending on your machine.

## Why robot builders care

Laser cutting gives you structural parts that are light, flat, and accurate. Chassis plates, motor mounts, standoffs, cable guides, and decorative panels all come out cleanly with edges you'd struggle to achieve by hand.

Flat-pack designs nest tightly on a sheet, so material waste is low. Plywood at 2–3 mm thickness is rigid enough for most small robot frames yet light enough to keep your robot nimble. Acrylic adds a professional finish or lets you show off the electronics inside.

Unlike 3D printing, there's no wait for layers to build up. A chassis that would take an hour to 3D print might take four minutes to cut. The trade-off is that you're working in 2D — you can't make organic curved forms, but clever joinery (finger joints, living hinges, press-fit tabs) gets you a long way.

## Get started

The best starting point is getting familiar with your laser cutter and the software that drives it. [LightBurn](https://lightburnsoftware.com) is the go-to application for most diode and CO₂ lasers — it handles both design and machine control. For free vector design, Inkscape works well.

Kevin's post [Robots and Lasers](/blog/robots-and-lasers.html) covers getting started with the Creality Falcon 5W, including LightBurn setup and cut settings. A great first build is [WoodBot](/blog/woodbot.html) — a complete laser-cut robot chassis made from 2 mm plywood and driven by an Arduino. It's a perfect project for learning how flat parts assemble into a three-dimensional robot.

Once you're comfortable with the basics, try a more ambitious project like the [C2Pi-O camera holder](/blog/c2pi_o.html) — a Star Wars–inspired laser-cut rig for two Raspberry Pi cameras.

Start simple: cut a flat test square, then a finger-jointed box. Once the kerf compensation clicks, you'll wonder why you ever reached for a hacksaw.
