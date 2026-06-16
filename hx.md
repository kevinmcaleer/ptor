---
layout: ptor
title: "Hx is for Hexapods — The Periodic Table of Robotics"
name: Hexapods
code: Hx
number: 82
category: robots
description: "Six-legged robots that walk like insects — stable, expressive, and a brilliant hands-on way to master servos and kinematics."
cover: /assets/img/ptor/og/hx.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - robot
  - servo
  - kinematics
  - 3d printing
related:
  - ik
  - sv
  - qd
  - ch
  - pr
---

Six legs. Eighteen servos. One robot that never stops being fascinating to watch.

Hexapods are insect-inspired walking robots, and they sit at a sweet spot for builders: complex enough to teach you real robotics concepts, but forgiving enough that beginners can get one moving in a weekend.

## What is a Hexapod?

A hexapod is a legged robot with six legs, each typically driven by two or three servos — one at the hip, one at the knee, and sometimes one at the "ankle". That adds up to twelve or eighteen servo channels on a full build.

The real magic is stability. With six legs, a hexapod can always keep at least three on the ground while the others move. That **tripod gait** means no complex balancing algorithms needed — the geometry handles it. A four-legged robot (quadruped) has to solve a balancing problem; a hexapod just walks.

Here's why the tripod gait is so stable. The six legs split into two interleaved tripods. While one tripod lifts and swings forward, the other three legs stay planted — and three planted feet always form a stable triangle the robot's weight sits inside:

```
        LEFT        RIGHT
   front  L1 ────── R1            Tripod A: L1, R2, L3
          |         |             Tripod B: R1, L2, R3
   mid    L2 ──[body]── R2
          |         |             Step 1: A planted, B swings
   rear   L3 ────── R3            Step 2: B planted, A swings
                                  …repeat → smooth walk

   ● = planted (down)   ○ = lifted (swinging)

      ● L1   R1 ○        ○ L1   R1 ●
      ○ L2   R2 ●   →    ● L2   R2 ○
      ● L3   R3 ○        ○ L3   R3 ●
       tripod A down       tripod B down
```

Because three feet are always down forming a triangle, the robot never has to actively balance — it simply can't fall over mid-step.

Most hexapods sit in the 150–300 mm body-width range for hobby builds, and the legs are usually 3D printed. You'll drive the servos from a microcontroller — a Raspberry Pi Pico, an ESP32, or a Raspberry Pi with a servo driver board.

## Why robot builders care

Hexapods teach you a concentrated bundle of skills in one project:

- **Servo control** — coordinating twelve or eighteen servos smoothly under load
- **Gait programming** — writing the timing sequences that make legs move in patterns (tripod, wave, ripple)
- **Inverse kinematics** — calculating the joint angles needed to put a foot at a precise point in space
- **Mechanical design** — building legs that are light, stiff, and don't bind under load
- **Power management** — eighteen servos stall-peak together; your power supply and batteries need to handle it

Even getting a basic forward walk working is enormously satisfying. From there you can add terrain sensing, remote control, or autonomous navigation.

## Get started

Start with a three-servo-per-leg design in CAD — or grab a printable design from Thingiverse — and work your way up. For the servo wiring, [bus servos like the Feetech STS3215](/blog/bus-servos.html) are brilliant for hexapods: they daisy-chain over a single data wire, give you position feedback, and dramatically cut down on the cable spaghetti you'd otherwise get with eighteen individual PWM leads. If you're using standard hobby servos, a [PCA9685 servo driver board](/learn/pca9685/01_course_introduction.html) lets one microcontroller address all eighteen channels over I2C.

Kevin's [PicoCrab 2](/blog/picocrab2.html) is a great example of what a compact, Pico-powered multi-legged build looks like — it shows the whole design-print-wire-program loop in one project. Read the [serial servos explainer](/blog/serial-servos.html) too; understanding servo communication protocols will save you hours of debugging once you scale up to a full hexapod.

Once the basic walk is working, dig into inverse kinematics. IK lets you specify where you want a foot to land and calculate the required joint angles automatically — it's what separates a hexapod that shuffles from one that steps with purpose.
