---
layout: ptor
title: "Ik is for Inverse Kinematics — The Periodic Table of Robotics"
name: Inverse Kinematics
code: Ik
number: 54
category: intelligence
description: "Tell your robot arm exactly where to reach, and let the maths figure out which joints to move — the secret to smooth, precise arm control."
cover: /assets/img/ptor/og/ik.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - robotics
  - robotarms
  - inverse_kinematics
  - python
  - servos
related:
  - ra
  - pd
  - sv
  - cv
  - ml
external_link: https://en.wikipedia.org/wiki/Inverse_kinematics
external_label: IK on Wikipedia
---

Imagine you want a robot arm to pick up a cup. You don't think about which muscles to contract — you just reach. Inverse kinematics (IK) lets your robot do the same thing.

## What is Inverse Kinematics?

Inverse kinematics is the maths that works backwards from a target position to the joint angles needed to reach it.

A robot arm has several joints — shoulder, elbow, wrist — each driven by a servo or motor. **Forward kinematics** asks "if I set these joint angles, where does the tip end up?" **Inverse kinematics** flips that question: "given the tip needs to be *here*, what should the joint angles be?"

Here's a 2-link arm laid out. The two segment lengths (`l1`, `l2`) and the two joint angles (`a1`, `a2`) are everything the maths needs to place the tip at a target `(x, y)`:

```
                       ● tip at (x, y)
                      /
                 l2  /
                    /
        a2 ╮  ●────╯  elbow joint
              \
          l1   \
                \
        a1 ╮     ● shoulder (base, at origin)
   ─────────────┴───────────────  ground

   l1, l2 = segment lengths      a1 = shoulder angle
   (x, y) = target position      a2 = elbow angle
```

Forward kinematics works left-to-right (angles → tip). Inverse kinematics runs it backwards (tip → angles) — which is the version you actually want when telling an arm "reach *there*".

For a simple 2-link arm in 2D, the answer is a bit of trigonometry — law of cosines, `atan2`, that sort of thing. Most hobby robot arms live in 2D or have limited degrees of freedom, so the maths stays manageable with a few lines of Python.

A typical 2-link solution looks something like this:

```python
import math

def inverse_kinematics(x, y, l1, l2):
    d = math.sqrt(x**2 + y**2)
    a2 = math.acos((d**2 - l1**2 - l2**2) / (2 * l1 * l2))
    a1 = math.atan2(y, x) - math.atan2(l2 * math.sin(a2), l1 + l2 * math.cos(a2))
    return math.degrees(a1), math.degrees(a2)
```

Pass in the arm segment lengths and the target position, and you get back two servo angles.

## Why robot builders care

Without IK, you're stuck manually tweaking servo angles until the arm reaches roughly the right place — tedious and fragile. With IK, you describe the target in real-world coordinates (centimetres from the base, say), and your code does the geometry. That makes it practical to control an arm from a camera feed, a joystick, or even a gesture sensor.

IK also pairs naturally with [PID control](/periodic-table/pd.html) to smooth out the motion between waypoints — instead of snapping from angle to angle, the arm glides.

## Get started

The best way to learn IK is to build a two-link arm and make it draw. Kevin's [Buddy Jr.](/blog/buddy_jr.html) project walks you through a small 4-servo robot arm on a Raspberry Pi, complete with Python code that uses IK to calculate joint angles — a great hands-on introduction.

The [PicoTico](/blog/pico-tico.html) TicTacToe robot is another real example: it uses IK to position a pen precisely on a grid, driven by a Raspberry Pi Pico.

For a broader look at arm projects — from simple pick-and-place to IK-driven builds — the [Robot Arms showcase](/blog/robot-arms.html) is a great starting point. And if you want to go deeper on programming a 4-servo arm from scratch, the [Building a Robot Arm with Raspberry Pi and PCA9685](/learn/pca9685/01_course_introduction.html) course covers the hardware and software end to end.

Start with a 2-link planar arm (two segments, two servos, move in a flat plane). Get the formula working in Python, then wire up real servos and watch the arm track your target coordinates. Once that clicks, adding a third axis — or a gripper — feels like a natural next step.
