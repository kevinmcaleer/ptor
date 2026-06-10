---
layout: ptor
title: "Ar is for Arduino — The Periodic Table of Robotics"
name: Arduino
code: Ar
number: 21
category: boards
description: "The open-source microcontroller board that gave millions of makers a simple, affordable path into electronics and robotics."
cover: /assets/img/ptor/og/ar.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - arduino
  - microcontroller
  - electronics
  - robotics
  - beginners
related:
  - pi
  - rp
  - es
  - cp
  - io
external_link: https://www.arduino.cc
external_label: Arduino.cc
---

Few boards have done more for robot builders than the Arduino. If you've ever wanted hardware to obey code without needing a degree in electrical engineering, this is where most people start.

## What is Arduino?

Arduino is an open-source electronics platform built around a simple microcontroller board and an easy-to-use programming environment. The classic board — the Uno — runs an ATmega328P chip at 16 MHz with 32 KB of flash memory and 2 KB of RAM. Those numbers sound modest, but they're enough to control motors, read sensors, flash LEDs, and drive servos.

The real magic is the ecosystem. Thousands of ready-made libraries handle everything from driving stepper motors to communicating over I2C. The IDE (now Arduino IDE 2) keeps things approachable: upload your first sketch in minutes, not hours. The language is a flavour of C/C++, but the learning curve is deliberately gentle — `setup()` and `loop()` are all you need to get going.

Modern Arduinos go well beyond the original Uno. The Nano ESP32 adds WiFi and Bluetooth. The Uno R4 Minima and WiFi bring a 32-bit ARM core. There's even the MKR family for IoT work. The family keeps growing, but the core idea stays the same: easy hardware access, approachable code.

## Why robot builders care

Arduino sits at the sweet spot between "too simple to be useful" and "too complex to start." You get direct hardware control — PWM outputs for motor speed, analogue inputs for distance sensors, digital pins for bumpers — without an operating system getting in the way. That matters when you need a motor to respond within milliseconds, not whenever Linux gets round to it.

The board is also cheap, widely stocked, and forgiving. Fry a pin? A replacement costs a few pounds. That freedom to experiment — and occasionally break things — is exactly what early-stage robot building needs.

## Get started

The fastest way in is to build something that moves. The [SMARS robot](/blog/smars.html) is a 3D-printed chassis designed from the ground up for Arduino and is a brilliant first build — Kevin's course [Learn how to program SMARS with Arduino](/learn/smars_code/01_lesson_01.html) walks you through every step from wiring the motors to writing your first drive routine.

If you already know a bit of Python and want to bring that to Arduino hardware, check out [Python and Arduino](/blog/pyfirmata.html) — it shows how PyFirmata lets you control Arduino pins directly from a Python script on your computer. And if you're ready to move on to MicroPython running *on* the board itself, the [Arduino to MicroPython Quick Start Guide](/learn/arduino_to_python/00_intro.html) gets you there with side-by-side code comparisons so nothing feels like starting over.

Pick a project, wire it up, and hit upload. That's really all it takes.
