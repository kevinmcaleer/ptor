---
layout: ptor
title: "Ir is for Infrared — The Periodic Table of Robotics"
name: Infrared
code: Ir
number: 32
category: sensors
description: "Invisible light that lets robots follow lines, dodge obstacles, and talk to remote controls — cheap, fast, and surprisingly versatile."
cover: /assets/img/ptor/og/ir.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - sensors
  - infrared
  - line-following
  - obstacle-detection
related:
  - us
  - dc
  - hb
  - mp
  - io
---

Infrared light is everywhere — in your TV remote, your security lights, and almost certainly the first robot sensor you'll ever wire up. It's invisible to human eyes, but your robot can use it to see the world.

## What is Infrared?

Infrared (IR) is light just beyond the red end of the visible spectrum, with wavelengths roughly between 700 nm and 1 mm. In robotics, two flavours matter most:

- **Proximity / reflectance sensors** — an IR LED shines light downward or forward; a photodetector measures how much bounces back. Dark surfaces absorb more light than pale ones, so the sensor can tell the difference between a black line on white card, or an obstacle at close range.
- **IR receivers** — a small demodulator chip (like the common TSOP38238) decodes modulated signals from remote controls. Great for giving your robot simple wireless commands without any radio hardware.

Most IR reflectance modules are 3-pin (VCC, GND, signal) and cost well under a pound. Obstacle-detection modules typically add a potentiometer so you can tune the detection distance.

## Why robot builders care

IR sensors punch above their weight for the price:

- **Line following** — two reflectance sensors under a chassis is the classic beginner build. The robot reads left and right, steers to stay on the line.
- **Obstacle detection** — a forward-facing IR module can stop your robot before it drives off a table or into the cat.
- **Remote control** — decode NEC-protocol signals from any TV remote and you have a dirt-cheap wireless interface for your project.
- **Edge detection** — mount sensors facing down to detect when the robot reaches the edge of a table (perfect for sumo bots or tabletop rovers).

Latency is near-zero compared to ultrasonic sensors, which makes IR great for fast, reactive control loops.

## Get started

The easiest first project is a **line-follower**. You need two IR reflectance modules, a motor driver, and a microcontroller — that's it.

The [MicroPython Robotics Projects with the Raspberry Pi Pico](/learn/micropython_robotics/01_intro.html) course walks through exactly this: wiring up IR sensors, reading their digital output, and writing the control logic to keep a robot on a black line. There's a dedicated lesson on line following with IR sensors built right in.

If you'd rather start with a ready-made robot, the [Cutebot and Cutebot Pro](/blog/cutebot.html) post covers a micro:bit robot that ships with dual line-following IR sensors and an ultrasonic sensor already fitted — handy if you want to see the finished hardware before you build your own.

A quick wiring tip: most cheap IR modules output **LOW when they detect a surface** (active low). Test yours with a simple print loop before assuming the logic level — it trips up almost everyone the first time.

Once you've got line following working, try combining IR with PWM motor control for smoother steering, or decode a TV remote to add manual override — two skills that make your robot feel genuinely alive.
