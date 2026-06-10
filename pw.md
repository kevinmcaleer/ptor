---
layout: ptor
title: "Pw is for PWM — The Periodic Table of Robotics"
name: PWM
code: Pw
number: 27
category: signals
description: "PWM lets a digital pin fake an analogue output — master it and you can dim lights, spin motors at any speed, and sweep servos to any angle."
cover: /assets/img/ptor/og/pw.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - micropython
  - electronics
  - servos
  - motors
related:
  - sv
  - io
  - dc
  - pi
  - hb
---

Your microcontroller's pins are either fully on or fully off. PWM is the clever trick that makes them behave like everything in between — and it's behind almost every moving part on your robot.

## What is PWM?

PWM stands for **Pulse Width Modulation**. Instead of outputting a steady voltage, a PWM pin rapidly switches between high and low many times per second. The ratio of time spent high versus the total cycle time is called the **duty cycle**, expressed as a percentage.

- **0 % duty cycle** — pin stays low. No output.
- **50 % duty cycle** — high half the time, low half the time.
- **100 % duty cycle** — pin stays high. Full output.

Because the switching happens so fast (typically 50 Hz to 1 kHz or more), the receiving device effectively sees an average voltage. That's how a digital chip can "fake" an analogue signal.

## Why robot builders care

Servo motors expect a **50 Hz PWM signal** where the pulse width (not the duty cycle percentage) sets the angle — typically 1 ms for 0°, 1.5 ms for 90°, and 2 ms for 180°. Get that pulse width right and you can position a servo arm exactly where you want it with a single line of code.

DC motors are different: you run them faster or slower by raising or lowering the duty cycle, usually through an H-bridge driver chip. A 30 % duty cycle spins the motor gently; 90 % and it's flat out.

PWM also handles LEDs. Fading an LED in and out is just a duty-cycle sweep — the LED reacts to the average power, not the individual pulses.

## Get started

The Raspberry Pi Pico has **up to 16 PWM channels** built in, accessible directly from MicroPython with just a few lines:

```python
from machine import Pin, PWM

servo = PWM(Pin(0))
servo.freq(50)          # 50 Hz for hobby servos
servo.duty_u16(4915)    # ~1.5 ms pulse — centre position
```

The [Raspberry Pi Pico GPIO Mastery course](/learn/micropython_gpio/00_intro.html) covers PWM hands-on, including how to calculate the correct duty values for servo positioning and motor speed control.

Once you need more than a couple of servos, you'll hit the Pico's channel limit fast. A **PCA9685 breakout board** solves this — it's a dedicated 16-channel PWM driver that offloads all the timing work over I2C, freeing your microcontroller to think about the bigger picture. The [Building a Robot Arm with Raspberry Pi and PCA9685 course](/learn/pca9685/01_course_introduction.html) builds exactly this kind of system from scratch.

For a complete robot project that puts PWM-controlled motors and sensors together, the [MicroPython Robotics Projects course](/learn/micropython_robotics/01_intro.html) is a natural next step — it goes from GPIO basics to autonomous robots, with motor control via PWM throughout.

A good first mini-project: wire up a single hobby servo to pin 0 on a Pico, run the code above, then change the `duty_u16` value between roughly 1638 (0°) and 8192 (180°) and watch it sweep.
