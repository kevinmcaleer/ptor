---
layout: ptor
title: "Tk is for Tank Tracks — The Periodic Table of Robotics"
name: Tank Tracks
code: Tk
number: 63
category: making
description: "Give your robot all-terrain grip — tank tracks let you climb over obstacles that would stop wheeled bots dead."
cover: /assets/img/ptor/og/tk.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - smars
  - robot
  - chassis
  - 3d-printing
related:
  - sm
  - ch
  - wh
  - pr
  - dc
---

Tank tracks turn a timid floor-crawler into a robot that shrugs at carpet, gravel, and ramps alike. If you've ever watched a wheeled bot get stuck on a cable or a door threshold, you'll appreciate what a continuous track brings to the table.

## What is Tank Tracks?

A tank track — or continuous track — is a loop of linked segments that wraps around two or more wheels (called drive sprockets and idler wheels). Instead of a single point of contact per wheel, the track spreads the robot's weight across a long flat surface. That means more grip, better stability, and the ability to climb small obstacles.

On small robots you'll usually see two independent tracks, one on each side. Steering works by varying the speed (or direction) of each track — spin both forward and you go straight, slow one side and you turn, reverse one while the other goes forward and you spin on the spot. This is called **differential drive**, or skid steering, and it's the same principle used in full-size bulldozers.

Track segments are typically driven by a DC motor through a simple gear train. The motor drives a sprocket, the sprocket meshes with the track, and the track loops around the idler wheel at the other end.

## Why robot builders care

Tracks solve real problems that wheels can't handle:

- **Rough terrain** — gravel, grass, and low lips that stop wheels don't faze a well-tensioned track.
- **Climbing** — a flat track footprint can bridge gaps and clamber over small steps.
- **Stability** — the wide contact patch lowers the centre of gravity, so the robot is harder to tip.
- **Predictable turning** — skid steering is mechanically simple. No steering servo needed.

The trade-off is friction. Turning on the spot scrubs the tracks against the ground, which takes more motor torque than a wheeled turn.

## Get started

The easiest way to try tracked locomotion is to build a [SMARS robot](/blog/smars.html) — the Screwless Modular Assemble-able Robotic System. SMARS was designed by Kevin from the ground up as a 3D-printable, snap-together tracked chassis. Everything — body, tracks, sprockets, and idler wheels — prints on a standard FDM printer with no supports needed.

Start with the [SMARS course](/learn/smars/00_intro.html), which walks you through printing the parts, assembling the chassis, and wiring up the motors. Once the hardware is running, move on to [programming SMARS with Arduino](/learn/smars_code/01_lesson_01.html) to make it drive autonomously.

If you want to customise the chassis shape first, the [Building SMARS with FreeCAD](/learn/freecad_smars/00_intro.html) course shows you how to adapt the iconic base to your own dimensions — a great exercise in understanding how track geometry and wheel spacing affect performance.

A concrete first project: print a SMARS, wire up two N20 gear motors to an H-bridge, and write a simple "drive forward, pause, spin 180°" loop. Once you can reliably navigate a figure-of-eight on the kitchen floor, you're ready to add a distance sensor and proper obstacle avoidance.
