---
layout: ptor
title: "Qd is for Quadrupeds — The Periodic Table of Robotics"
name: Quadrupeds
code: Qd
number: 81
category: robots
description: "Four-legged robots that walk, trot and balance — from 3D-printed robot cats to full robot dogs, quadrupeds are legged locomotion at its most accessible."
cover: /assets/img/ptor/og/qd.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - picocat
  - robot
  - servos
  - gait
related:
  - pc
  - hx
  - sv
  - ik
  - sm
---

Four legs, twelve servos, and a whole lot of coordination — quadruped robots are the point where robotics stops being abstract and starts looking alive.

## What is a Quadruped?

A quadruped is any robot with four legs. In biology that covers dogs, cats, horses and lizards. In robotics, it means a machine that uses four independently actuated limbs to walk across a surface rather than rolling on wheels or tracks.

Most hobby quadrupeds use **three servos per leg** — one at the hip, one at the knee, and one at the shoulder — giving twelve servos total. Each leg can swing forward and back, lift and lower, and splay outwards. Coordinating all twelve servos in a smooth, stable sequence is what gait programming is all about.

## The support triangle

Here's the balancing problem a quadruped has to solve. When one leg lifts to step, the other three form a **support triangle**. The robot stays upright only as long as its **centre of mass** sits inside that triangle — so before lifting a leg, the robot first shifts its weight over the other three:

```
   All four down            Front-left lifted (○)

   FL ●──────● FR           FL ○      ● FR
      │ body │                   ╲    ╱│
      │  ×   │  × = centre        ╲ × ╱ │   weight shifted
      │ mass │      of mass        ╲ ╱  │   so × stays inside
   RL ●──────● RR           RL ●───●────● RR
                                  the support
                                  triangle (3 feet)

   × inside the triangle → stable
   × outside it          → tips over
```

This is exactly why three servos per leg matters: the robot needs to lift, swing *and* shift weight sideways — and coordinating that across twelve servos is the heart of gait programming.

Popular platforms include the [OpenCat](https://www.petoi.com) family of robot cats, Boston Dynamics' Spot (at the professional end of the scale), and homegrown designs like SMARS Quad and PicoCat. Microcontrollers from the Raspberry Pi Pico to full single-board computers can act as the brain.

## Why robot builders care

Wheels are simple. Legs are interesting. Quadrupeds force you to think about problems that wheeled robots sidestep entirely:

- **Gait sequencing** — which legs move in which order, and when? A trot, walk, and bound are all different movement patterns.
- **Balance and stability** — while three legs are on the ground the centre of mass must sit inside the support triangle, or the robot tips over.
- **Inverse kinematics** — rather than telling each servo what angle to be at, you tell the foot where to land and let the maths work out the joint angles. This is the real skill that quadrupeds teach.
- **Terrain adaptation** — a wheeled robot stops at a kerb; a legged robot can step over it.

These are the same challenges engineers tackle at Boston Dynamics and Unitree. Building a small quadruped at home is the best possible introduction to that world.

## Get started

The gentlest starting point is the **[SMARS Quad course](/learn/smars_quad/00_intro.html)** — it walks you through 3D printing, assembling, and programming a four-legged SMARS variant. The mechanics are clear, the code is approachable, and you end up with a robot that genuinely walks.

If you want something more cat-shaped, the **[PicoCat v2 project page](/blog/picocat-v2.html)** covers Kevin's open-source robot cat built on a Raspberry Pi Pico with twelve servos. The **[PicoCat Lives build log](/blog/picocat-lives.html)** has the full parts list and STL downloads.

For historical context and a look at the OpenCat platform that inspired PicoCat, the **[OpenCat project post](/blog/opencat.html)** is worth a read.

Once you have a robot walking, the natural next step is inverse kinematics — feeding target foot positions into the maths rather than hard-coding every servo angle. It sounds scary, but once it clicks, your robot goes from shuffling to striding.
