---
layout: ptor
title: "Us is for Ultrasonic — The Periodic Table of Robotics"
name: Ultrasonic
code: Us
number: 31
category: sensors
description: "Bounce sound off the world and measure the echo — the HC-SR04 is the sensor that gives almost every beginner robot its first pair of eyes."
cover: /assets/img/ptor/og/us.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - sensors
  - smars
  - micropython
  - raspberry pi pico
related:
  - ir
  - ld
  - im
  - pd
  - sm
external_link: https://cdn.sparkfun.com/datasheets/Sensors/Proximity/HCSR04.pdf
external_label: HC-SR04 Datasheet
---

Point a sensor at a wall, fire a burst of sound, and count how long the echo takes to return. That's ultrasonic distance sensing — simple physics that turns your robot from a blind object into something that can actually see where it's going.

## What is Ultrasonic?

An ultrasonic distance sensor emits a short burst of sound at around 40 kHz — well above human hearing — and listens for the echo. Because sound travels at roughly 343 m/s in air, you can calculate distance with one formula:

```
distance (cm) = (echo time in microseconds) / 58
```

The HC-SR04 is the sensor you'll find on almost every beginner robot. It has four pins: `VCC`, `GND`, `Trig`, and `Echo`. Pull `Trig` high for 10 microseconds to fire, then time how long `Echo` stays high. Measuring range is roughly 2 cm to 400 cm, with accuracy around ±3 mm on a good day. At under £2 a unit, it's hard to beat.

## Why robot builders care

Without distance sensing, your robot crashes. Constantly. An ultrasonic sensor gives your robot the ability to detect obstacles before it hits them, so you can write logic to stop, turn, and find a new path.

It's also the sensor that makes radar-style scanning possible. Mount one on a servo, sweep it through an arc, and log the readings — you've just built a sonar map of your robot's surroundings. That's genuinely useful for navigation and it looks brilliant on a display.

Ultrasonic sensors work in the dark, they don't care about object colour, and they're forgiving of beginner wiring mistakes. That combination makes them the go-to first sensor for almost every robot project.

## Get started

The best first project is simple: wire an HC-SR04 to a Raspberry Pi Pico, read the distance in a loop, and print it to the serial console. Once the numbers make sense, add an LED that changes colour when something gets within 20 cm.

The [GPIO Mastery course for Raspberry Pi Pico with MicroPython](/learn/micropython_gpio/00_intro.html) has a dedicated lesson walking you through exactly that wiring and code — it covers the `Trig`/`Echo` pulse timing and gives you a complete working MicroPython snippet.

When you're ready for something more ambitious, the [Radar Robot project](/blog/radar-robot.html) mounts an HC-SR04 on a servo and sweeps it across a 180° arc, drawing a live sonar display. It's a fantastic way to understand how autonomous robots build a picture of their environment.

The SMARS robot — probably the most-built robot on this site — uses an HC-SR04 as its main obstacle detector. The [SMARS course](/learn/smars/00_intro.html) covers the full build, including how to write the obstacle-avoidance code that puts the sensor to work.
