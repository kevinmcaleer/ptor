---
layout: ptor
title: "Hu is for Humanoids — The Periodic Table of Robotics"
name: Humanoids
code: Hu
number: 80
category: robots
description: "Robots shaped like people — two legs, two arms, a head — tackling the hardest problems in locomotion, balance, and machine intelligence."
cover: /assets/img/ptor/og/hu.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - robot
  - ai
  - humanoid
  - servo
related:
  - ik
  - sv
  - qd
  - ml
  - au
---

Humanoids are robotics in hard mode. Building a machine that walks upright, keeps its balance, uses its hands, and interacts naturally with people pushes every skill you have — and then some.

## What is a Humanoid?

A humanoid robot is any robot with a roughly human-shaped body: an upright torso, two arms, two legs, and usually a head. That last bit matters more than it sounds — human environments (stairs, door handles, furniture at hip height) were designed for bodies shaped like ours, so a robot that shares our proportions can navigate those spaces without the world being redesigned around it.

The engineering challenges stack up fast. A bipedal robot has to solve **dynamic balance** in real time — unlike a wheeled robot, a standing humanoid is constantly on the edge of falling over and must shift its weight with every step. Smaller hobby humanoids cheat a little by moving slowly and keeping their centre of mass low, but the problem never fully goes away.

A typical maker-scale humanoid uses **18–20 servo joints**: three per leg (hip, knee, ankle), three per arm (shoulder, elbow, wrist), plus a neck. Servo choice matters enormously — a servo that's fine for a robot arm can't hold a walking robot upright through a stride.

Here's where those joints sit. Each ● is a servo; the legs carry the most demanding ones because they bear the robot's whole weight through every step:

```
                 ● neck
              ┌──┴──┐
       ● shoulder  shoulder ●
         │  [ torso ]  │
       ● elbow      elbow ●
         │              │
       ● wrist      wrist ●     each ● = 1 servo joint
              ┌──┴──┐
        ● hip        hip ●      legs: hip + knee + ankle
          │            │        arms: shoulder + elbow + wrist
        ● knee      knee ●      + 1 neck
          │            │
        ● ankle    ankle ●      ≈ 18–20 joints total
        ▭ foot      foot ▭
```

The legs are where the real challenge lives: a bipedal robot is always on the edge of toppling, so it must shift its centre of mass over the planted foot with every single step — which is why leg servos need far more torque (and better control) than the arms.

## Why robot builders care

Humanoids are the grand challenge of robotics for a reason. Almost every other element in this table feeds into one: servo control, inverse kinematics, PID loops, computer vision, AI, battery management, 3D printing, chassis design. Building even a simple bipedal robot forces you to understand how all those pieces interact.

They're also deeply compelling to watch. There's something uniquely satisfying about a machine you built standing up, shifting its weight, and taking a step. People will crowd around a walking humanoid in a way they rarely do for anything else.

And if it falls over? That's robotics telling you something useful about physics.

## Get started

The friendliest entry point is a small 3D-printed humanoid with hobby servos. Kevin's project [Chip — Cute Humanoid Interactive Pal](/blog/chip.html) is a great example: a printable bipedal robot driven by 18 servos on a Pimoroni Servo 2040 board and programmed in MicroPython. It moves slowly enough to debug and gives you a real taste of bipedal locomotion challenges.

For the servo control side of things, [How Serial Servos Work](/blog/serial-servos.html) explains why smart bus servos — which report back their position and can be daisy-chained — are a significant upgrade over plain PWM servos for multi-joint builds like humanoids.

If you want to think bigger, [Where Is My Robot Butler?](/blog/robot-butler.html) explores why full domestic humanoids are still so hard, covering the battery, dexterity, and AI challenges that even well-funded labs are still chipping away at.

Once you've got a humanoid moving, look at inverse kinematics to make arm and leg positioning feel natural, and study gait theory — the patterns of weight transfer that turn a sequence of servo moves into something that actually looks like walking.
