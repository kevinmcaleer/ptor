---
layout: ptor
title: "Mb is for micro:bit — The Periodic Table of Robotics"
name: "micro:bit"
code: Mb
number: 25
category: boards
description: "The pocket-sized BBC board that makes coding physical — blink LEDs, read sensors, and drive robots from day one."
cover: /assets/img/ptor/og/mb.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - microbit
  - education
  - beginners
  - micropython
related:
  - pi
  - ar
  - sc
  - mp
  - io
external_link: https://microbit.org
external_label: microbit.org
---

The micro:bit might be small enough to fit in your pocket, but it packs a real punch for anyone just starting out with hardware and code. It's the board that genuinely earns the label "designed for learning" — without feeling like it's limiting you.

## What is micro:bit?

The BBC micro:bit is a small ARM-based microcontroller board originally developed in partnership with the BBC to put coding into the hands of every UK secondary school pupil. It measures just 4 × 5 cm and comes loaded with hardware you can use straight away: a 5×5 LED matrix, two programmable buttons, a built-in accelerometer, compass, temperature sensor, light sensor, speaker, microphone, and a Bluetooth radio. Version 2 (released 2020) added the speaker and microphone, making it genuinely capable out of the box.

You program it in MicroPython, JavaScript Blocks, or the web-based MakeCode editor — no drivers, no toolchain setup, just drag-and-drop in a browser or type Python into the online editor and hit download. Plug in via USB, copy the file across, done.

## What's on the board

Almost everything you need for a first robot is already built in. The front carries the LED grid and two buttons; sensors and the radio live on the board itself; the gold-fingered edge connector along the bottom breaks out the GPIO for motors and servos:

```
   ┌──────────────────────────────┐
   │  [A]   ● ● ● ● ●        [B]   │  ← 2 buttons +
   │        ● ● ● ● ●              │    5×5 LED matrix
   │        ● ● ● ● ●              │
   │        ● ● ● ● ●              │  on-board (not shown):
   │        ● ● ● ● ●              │  accelerometer, compass,
   │                              │  mic, speaker, BLE radio
   └──┬─┬─┬──────────┬─┬─┬─┬─┬─┬──┘
      0 1 2          3V GND  …  ← edge connector
      └─ GPIO: motors, servos, sensors ─┘
```

The radio is the standout for robots: two micro:bits can talk to each other straight out of the box, so one becomes a handheld controller and the other the robot — no WiFi setup, no pairing faff.

## Why robot builders care

The micro:bit is a brilliant first brain for a robot. The onboard accelerometer means you can tilt it to steer. The radio lets two micro:bits talk to each other, so you can build a hand-held controller for your chassis without touching WiFi config. The edge connector has GPIO pins for motors, servos, and sensors — attach an expansion board and you have a full robotics platform in minutes.

Boards like the Elecfreaks Cutebot sit a micro:bit on top and give you two DC motors, NeoPixel lights, and ultrasonic sensor ports. You code the intelligence on the micro:bit; the expansion board handles the power and the motor driver. That separation is actually a great way to learn what a motor driver *is* before you wire one up yourself.

Because the barrier to entry is so low, you spend your time thinking about the robot's behaviour rather than fighting your tooling. That's exactly what you want early on.

## Get started

The simplest first project is a "clap to drive" bot: use the onboard microphone (V2) or a button to trigger a movement, read the accelerometer to steer, and output PWM to a motor driver on the edge connector. You'll touch sensors, logic, and actuation in one go.

For a ready-made chassis, the [Cutebot & Cutebot Pro](/blog/cutebot.html) post walks through a micro:bit-based robot that drives, detects obstacles, and follows lines — all without soldering. If you fancy a different angle, [Retro Arcade](/blog/retro-arcade.html) shows how to build a handheld game console around the micro:bit, which is a great way to understand the button and display APIs before you apply them to robot control.

Once you're comfortable, move on to writing more complex MicroPython — the skills transfer directly to the Raspberry Pi Pico and beyond.
