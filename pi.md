---
layout: ptor
title: "Pi is for Raspberry Pi Pico — The Periodic Table of Robotics"
name: Raspberry Pi Pico
code: Pi
number: 23
category: boards
description: "The £4 microcontroller that sparked a maker revolution — tiny, fast, and ideal for driving robot motors, sensors, and servos."
cover: /assets/img/ptor/og/pi.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - pico
  - raspberry pi pico
  - micropython
  - microcontroller
related:
  - mp
  - io
  - pw
  - es
  - ar
external_link: https://www.raspberrypi.com/products/raspberry-pi-pico/
external_label: raspberrypi.com
---

Four pounds. Two cores. Infinite projects. The Raspberry Pi Pico is one of the most capable bits of kit you can drop into a robot build — and it fits on a breadboard.

## What is the Raspberry Pi Pico?

The Raspberry Pi Pico is a microcontroller board built around the RP2040 chip, designed by the Raspberry Pi Foundation and launched in January 2021. Unlike a Raspberry Pi computer, it does not run Linux — it runs your code directly on the chip, with nothing in between.

The headline specs are genuinely impressive for the price:

- **Dual-core Arm Cortex-M0+** running at up to 133 MHz
- **264 KB of SRAM** and 2 MB of onboard flash
- **26 GPIO pins**, including 3 analogue inputs
- **Hardware PWM** on every GPIO pin
- **I2C, SPI, UART** — all the serial protocols robots need
- **USB 1.1** for programming and serial comms

The Pico W adds 2.4 GHz WiFi (and Bluetooth on the Pico 2W), turning your robot into a wirelessly connected machine for about £6.

## Why robot builders care

Microcontrollers are the right tool for real-time control. When your robot needs to read an ultrasonic sensor every 10 ms, pulse a servo at exactly 50 Hz, and spin two DC motors at different speeds — all at once — a microcontroller handles that without flinching.

The Pico does all of this with hardware-level precision. Its Programmable I/O (PIO) blocks can even implement custom protocols in hardware if you need something unusual.

The price matters too. You can put a Pico inside every robot you build without worrying about the cost. Break one? Replace it for the price of a coffee. That freedom encourages experimentation — which is exactly how you get better at robotics.

MicroPython support is first-class on the Pico, so you can write readable Python code and have it running on hardware in minutes. C/C++ is fully supported if you need every last bit of performance.

## Get started

The quickest first step is flashing MicroPython onto your Pico. Hold the BOOTSEL button, plug in USB, and drag the `.uf2` firmware file onto the drive that appears. The whole process takes under two minutes. Then open [Thonny](https://thonny.org) and you have a live Python prompt talking directly to your hardware.

The [Raspberry Pi Pico with MicroPython — GPIO Mastery](/learn/micropython_gpio/00_intro.html) course is a solid introduction to controlling real hardware — LEDs, buttons, and sensors — from Python code.

Once you have the basics, [MicroPython Robotics Projects with the Raspberry Pi Pico](/learn/micropython_robotics/01_intro.html) takes you through motors, servos, and sensor-driven behaviour — everything you need to build a moving robot.

For inspiration on what the Pico can actually do, [10 Projects for your Raspberry Pi Pico](/blog/pico-projects.html) covers a brilliant range of builds, from simple gadgets to full robots.

The Pico's combination of low cost, solid documentation, and strong community makes it the ideal first microcontroller for robot builders. Start simple, build something that moves, and go from there.
