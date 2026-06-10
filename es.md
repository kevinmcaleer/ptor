---
layout: ptor
title: "Es is for ESP32 — The Periodic Table of Robotics"
name: ESP32
code: Es
number: 24
category: boards
description: "A tiny, cheap microcontroller with WiFi and Bluetooth built right in — the go-to chip for connected robots and IoT projects."
cover: /assets/img/ptor/og/es.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - esp32
  - microcontroller
  - wifi
  - micropython
  - iot
related:
  - wi
  - bl
  - mp
  - mq
  - pi
external_link: https://www.espressif.com/en/products/socs/esp32
external_label: Espressif ESP32
---

For less than the price of a coffee, the ESP32 puts a dual-core processor, WiFi, and Bluetooth on a board smaller than a credit card. It's remarkable what a few pounds of silicon can do these days.

## What is ESP32?

ESP32 is a microcontroller system-on-chip (SoC) made by Espressif Systems. The original ESP32 packs two Xtensa LX6 cores running up to 240 MHz, 520 KB of SRAM, and — crucially — both 802.11 b/g/n WiFi and Bluetooth 4.2 (plus BLE) baked right onto the chip. No extra modules, no extra cost.

The chip family has grown since the original. The ESP32-S3 adds faster cores and USB OTG. The ESP32-C3 is a single-core RISC-V variant for ultra-budget builds. The ESP32-CAM variant bolts on a camera module for a complete vision system at pocket-money prices.

You can program it with Arduino-style C++, MicroPython, or CircuitPython. Development boards like the DOIT DevKit, the Wemos D32, and the M5Stack family expose all those pins in a breadboard-friendly form, so you're never far from getting code running.

## Why robot builders care

Most microcontrollers make you add a separate WiFi or Bluetooth module if you want wireless — that's extra components, extra wiring, and extra things to go wrong. The ESP32 skips all of that. You can stream sensor data to a dashboard, receive commands over MQTT, or connect to a mobile app without touching a single extra chip.

That makes it perfect for:

- **Remote-controlled robots** — receive joystick commands over WiFi or Bluetooth from a phone or laptop.
- **Telemetry** — push battery voltage, motor speeds, or sensor readings to a server in real time.
- **Camera bots** — the ESP32-CAM streams live video over HTTP with just a handful of lines of code.
- **Swarm experiments** — multiple cheap ESP32 nodes can talk to each other or to a central broker using MQTT.

The dual-core architecture also means you can run your control loop on one core while the WiFi stack runs on the other — no awkward juggling of network calls inside your robot's main loop.

## Get started

The easiest first step is to install MicroPython on an ESP32 board and get it talking wirelessly. Kevin's guide [How to Install MicroPython](/blog/how-to-install-micropython.html) covers the flashing process step by step, and MicroPython's `network` module makes connecting to WiFi a five-line job.

Once the board is online, try sending commands over MQTT — it's a lightweight publish/subscribe protocol that works brilliantly for robot control. The [MicroPython Robotics Projects](/learn/micropython_robotics/01_intro.html) course builds real moving robots with MicroPython and covers exactly this kind of wireless control.

If you want to go further with vision, the post [Stream ESP32CAM Video](/blog/esp32cam-to-python.html) shows how to grab a live video stream from an ESP32-CAM and process it in Python on a Raspberry Pi — a great foundation for a camera-equipped rover.

Pick up a dev board, flash MicroPython, and watch your robot gain eyes and ears over the air.
