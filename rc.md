---
layout: ptor
title: "Rc is for Radio Control — The Periodic Table of Robotics"
name: Radio Control
code: Rc
number: 66
category: signals
description: "Pilot your robot from a distance using RF transmitters, Bluetooth gamepads, or Wi-Fi — giving you eyes-free control over any build."
cover: /assets/img/ptor/og/rc.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - bluetooth
  - robot
  - remote_control
  - wireless
  - micropython
related:
  - bl
  - wi
  - mq
  - dc
  - sm
---

There is something deeply satisfying about watching a robot you built respond to your thumbs. Radio control turns a static machine into something alive.

## What is Radio Control?

Radio Control (RC) is the practice of operating a robot or vehicle wirelessly from a handheld transmitter. Classic RC uses dedicated radio frequencies — 2.4 GHz spread-spectrum being the modern standard — but the term has expanded to cover any wireless control method: Bluetooth gamepads, Wi-Fi web interfaces, and even IR remotes.

A typical RC link has two ends: a **transmitter** (what you hold) and a **receiver** (on the robot). The receiver decodes incoming signals and passes commands to motor controllers, servos, or a microcontroller. Latency matters — anything above 100 ms feels sluggish when you are driving fast.

Key specs to know:
- **Range** — 2.4 GHz RC gear typically reaches 100–500 m outdoors. Bluetooth Classic/BLE tops out around 10–30 m indoors.
- **Channels** — one per independent axis of control. A ground robot needs 2 (throttle + steering); a hexapod may need 12+.
- **Protocol** — PWM, PPM, SBUS, and CRSF are common receiver output formats.

## Why robot builders care

Most beginner robots start autonomous, then hit a wall: "how do I test it without it crashing into the cat?" RC solves that immediately. You can drive the robot manually to verify mechanics, tune motor speeds, and test sensors — all before writing a single line of autonomous code.

RC is also the right tool when full autonomy is overkill. Combat robots, camera rovers, and teaching demos all benefit from a human in the loop.

The maker-friendly option these days is Bluetooth. A Raspberry Pi Pico W or ESP32 can pair with a cheap USB gamepad or phone app with only a few lines of MicroPython, giving you the RC feel without buying dedicated radio gear.

## Get started

The quickest on-ramp is a Bluetooth remote using the Pico W. Kevin built exactly this — a [Bluetooth remote controlled robot](/blog/bluetooth-remote.html) using a Raspberry Pi Pico W and MicroPython, complete with code to get you moving in an afternoon. He later turned that project into a [custom Bluetooth remote control PCB](/blog/bluetooth-remote-pcb.html), which is a brilliant next step once the software side clicks.

The [MicroPython Robotics Projects with the Raspberry Pi Pico](/learn/micropython_robotics/01_intro.html) course ties wireless control together with motors and chassis, walking you through remotely controlled robots from scratch.

Once basic RC is working, try these:

1. **Add a dead-man switch** — the robot stops if it loses signal. Essential for anything fast or heavy.
2. **Mix channels in software** — combine a joystick's X and Y axes into left/right motor speeds (differential drive mixing).
3. **Layer autonomy on top** — use RC to set waypoints or switch between manual and auto mode.

The moment you put a controller in someone else's hands and they can drive your robot, it stops being a project and starts being a toy. That is when the real fun begins.
