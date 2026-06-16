---
layout: ptor
title: "Ra is for Robot Arms — The Periodic Table of Robotics"
name: Robot Arms
code: Ra
number: 77
category: robots
description: "From a single servo gripper to a six-axis desktop arm — robot arms put reach, precision, and mechanical dexterity right on your workbench."
cover: /assets/img/ptor/og/ra.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - robotarms
  - servo
  - 3dprinting
  - inversekinematics
related:
  - sv
  - ik
  - pd
  - hx
  - qd
---

Robot arms are the classic image of robotics made real — and building one yourself teaches you more about motion, control, and mechanical design than almost any other project.

## What is a Robot Arm?

A robot arm is a chain of rigid links connected by joints, each joint driven by a motor — usually a servo. The simplest have three joints and three degrees of freedom (DOF). More capable designs reach four, five, or six DOF, which lets the end effector (the gripper or tool at the tip) reach almost any position and orientation within its workspace.

Desktop robot arms built by makers typically span a reach of **150–400 mm** and use hobby servos rated from 1.8 kg·cm (SG90) up to 15+ kg·cm for the shoulder joint, which bears the most load.

Here's how the joints chain together. Each joint adds one **degree of freedom (DOF)** — one more way the tip can move. A typical beginner arm has four: base rotation, shoulder, elbow, and a gripper at the end:

```
                          ┌─[ gripper ]   ← end effector
                          │     (open/close)
                   wrist ─●
                        ╱
                  elbow ●        each ● = a joint
                       │          (one servo,
            shoulder ──●           one DOF)
                       │
                  base ▼  ← rotates the whole arm
              ════════════  bench

   base + shoulder + elbow + gripper = 4 DOF
   more joints = the tip can reach more
   positions AND angles within its workspace
```

The shoulder bears the most load (it lifts everything above it), which is why it gets the beefiest servo.

Controlling where the tip ends up from a set of joint angles is called **forward kinematics**. Working backwards — given a target position for the tip, calculate what angles each joint needs — is **inverse kinematics**. That second problem is where the maths gets genuinely interesting, and where a lot of the robot arm magic lives.

## Why robot builders care

A robot arm is a complete education in one project. You touch mechanical design (linkage lengths, joint placement, balancing torque), electronics (servo drivers, power management), programming (PWM, easing, coordinate maths), and control theory (PID loops, smooth trajectories) — all in one build.

They're also just satisfying. Watching a machine you designed and printed reach across a desk and pick up a small object never gets old. Arms scale well too: a beginner can build a three-servo wrist from a kit in an afternoon; an intermediate builder can design a full six-axis arm in CAD and print every part.

## Get started

The best first step is a three- or four-servo arm you can build and wire in a weekend. Kevin's course [Building a Robot Arm with Raspberry Pi and PCA9685](/learn/pca9685/01_course_introduction.html) walks you from unboxing the PCA9685 servo driver board through Python code that moves a four-servo arm to target positions.

If you want to start even simpler, the [Simple Robot Arm](/blog/simple-robot-arm.html) project shows a 3D-printed arm controlled over Wi-Fi using a Raspberry Pi Pico W — you can jog each joint from a web page without writing a single line of inverse kinematics.

When you're ready for a real kit, have a look at the [MeArm](/blog/mearm.html) — a laser-cut acrylic four-DOF arm that's excellent value and well-documented.

Once your arm is moving reliably, consider upgrading to bus servos. The [Why are Bus Servos better?](/blog/bus-servos.html) post explains how daisy-chained smart servos give you position feedback, reduce wiring clutter, and make multi-joint arms far easier to control.

One practical tip: always balance your arm's centre of mass over the base, and add an end-stop in software before you ever run full-range motion. Robot arms can move fast and with enough torque to damage themselves or nearby objects. A short safe-home routine at startup saves a lot of grief.
