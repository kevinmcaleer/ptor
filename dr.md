---
layout: ptor
title: "Dr is for Drones — The Periodic Table of Robotics"
name: Drones
code: Dr
number: 79
category: robots
description: "Drones put your robotics skills to work in three dimensions — flight, sensors, autonomy, and real-time control all at once."
cover: /assets/img/ptor/og/dr.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - drone
  - robot
  - autonomous
  - flight
related:
  - im
  - pd
  - nv
  - au
  - rv
---

Drones are where robotics leaves the ground. A drone forces you to think about three-dimensional movement, real-time sensor fusion, and split-second control — all at once.

## What is a Drone?

A drone (technically an Unmanned Aerial Vehicle, or UAV) is any aircraft that flies without a pilot on board. In the maker world this usually means a **quadcopter** — four brushless motors on a cross-shaped frame, each spinning a propeller. By varying the speed of individual motors, the flight controller can make the craft hover, pitch, roll, yaw, and translate in any direction.

The key components are:

- **Frame** — the carbon fibre or 3D-printed body
- **Brushless motors and ESCs** (Electronic Speed Controllers) — convert digital commands into spin
- **Flight controller** — a small computer running firmware like Betaflight or ArduPilot
- **IMU** (accelerometer + gyroscope) — tells the controller which way is up
- **Battery** — usually a 3S or 4S LiPo pack; weight and capacity are a constant trade-off
- **Radio receiver** — takes your stick inputs and sends them to the flight controller

## The four-motor layout

A quadcopter's control trick is in how the four motors spin. **Diagonal pairs spin the same way** — two clockwise, two counter-clockwise — so their twisting forces cancel out and the craft doesn't spin on the spot. Change the balance of speeds and you get every movement:

```
        FRONT
     M1 ↺      M2 ↻
       \      /
        \    /
         [FC]        M1, M4 spin ↺ (CCW)
        /    \       M2, M3 spin ↻ (CW)
       /      \
     M3 ↻      M4 ↺
         REAR

   All four equal      → hover
   All four faster     → climb
   Speed up rear pair  → pitch forward (fly ahead)
   Speed up one side   → roll
   Speed up one ↺ pair → yaw (spin to face a new way)
```

The flight controller runs a PID loop thousands of times a second, nudging individual motor speeds to hold the craft steady — far faster than any human could react.

## Why robot builders care

Almost every skill you pick up on a ground robot transfers straight up into the air — and then gets harder, because nothing saves you if the software falls over.

**PID control** is what keeps the drone level. The flight controller runs a PID loop thousands of times a second to correct any tilt before you can even see it.

**Sensor fusion** matters enormously. An IMU alone drifts; GPS alone is too slow. Real autonomous drones blend multiple sources — IMU, barometer, optical flow, GPS — into a single position estimate.

**Autonomy and navigation** are the hard part. An FPV racer is essentially a remote-controlled aircraft. An autonomous drone needs waypoint planning, obstacle avoidance, and a reliable way to know where it is at all times.

## Get started

You don't need to build a drone from scratch to learn how they work. Start by understanding the software stack:

- **ArduPilot** and **PX4** are the two dominant open-source flight stacks. Both have simulators (SITL — Software In The Loop) so you can fly virtually before touching real hardware.
- **Betaflight** is the go-to firmware for FPV racing quads, and a great way to learn PID tuning hands-on.
- If you already know MicroPython, the [MicroPython Robotics course](/learn/micropython_robotics/01_intro.html) covers motor control and sensor reading — the same fundamentals a flight controller uses.
- For the broader robotics context — including how autonomy, sensing, and control fit together — the [Robotics 101 course](/learn/robotics_101/00_overview.html) is a solid foundation.
- Want to see autonomous navigation in action on a real robot first? The [Arduino Alvik maze navigation](/blog/alvik-maze.html) post walks through wall-following and early SLAM concepts that translate directly to drone path planning.

Once you're ready for hardware, consider starting with a small **Tiny Whoop** style micro-quad indoors, or a ready-to-fly platform, before moving on to custom builds. The physics are the same; the consequences of a crash are much kinder.
