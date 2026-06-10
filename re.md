---
layout: ptor
title: "Re is for Resistors — The Periodic Table of Robotics"
name: Resistors
code: Re
number: 19
category: foundations
description: "Tiny but mighty, resistors limit and divide current — protecting your LEDs, sensors, and microcontroller pins from an early death."
cover: /assets/img/ptor/og/re.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - components
  - circuits
related:
  - oh
  - el
  - ci
  - tr
  - io
---

Every robot project you'll ever build will contain at least one resistor. They're the unsung heroes sitting quietly on your breadboard, keeping everything else alive.

## What is a Resistor?

A resistor is a passive electronic component that opposes the flow of electrical current. The more resistance, the less current gets through. Resistance is measured in **ohms (Ω)** — named after Georg Simon Ohm, who worked out the relationship between voltage, current, and resistance back in the 1820s.

You'll find resistors in values ranging from a few ohms up to megaohms (millions of ohms). Common values you'll reach for time and again:

- **220Ω** — protecting an LED from a 3.3V or 5V GPIO pin
- **10kΩ** — pull-up or pull-down resistors for buttons and switches
- **1kΩ** — general-purpose current limiting

Resistors come in through-hole (those small cylinders with coloured stripes) and surface-mount (tiny rectangles on a PCB). Through-hole resistors are what you'll use on a breadboard. Read the value from the colour bands printed on the body.

## Why Robot Builders Care

Your microcontroller's GPIO pins — whether on a Raspberry Pi Pico, Arduino, or ESP32 — can typically only source or sink around 10–20 mA of current. LEDs and other components will happily draw far more than that and burn themselves out (or fry the pin) without something to limit the flow.

Resistors do three important jobs in robot circuits:

1. **Current limiting** — protect LEDs, transistors, and sensitive inputs
2. **Pull-up / pull-down** — hold a GPIO pin at a known logic level when a button isn't pressed
3. **Voltage dividers** — scale a signal down, for example making a 5V sensor output safe for a 3.3V input pin

Understanding resistors means you can wire up sensors, buttons, LEDs, and motor drivers with confidence rather than crossing your fingers and hoping nothing gets hot.

## Get Started

The best way to get comfortable with resistors is to wire up an LED correctly. Connect a 220Ω resistor in series between a GPIO pin and the positive leg of an LED, then connect the other LED leg to ground. That one resistor is the difference between a working circuit and a dead LED.

The [Raspberry Pi Pico GPIO Mastery course](/learn/micropython_gpio/00_intro.html) walks you through exactly this — blinking LEDs, reading buttons (with pull-down resistors), and using potentiometers (variable resistors) to control things with a twist of a dial.

If you want a broader look at how power, voltage, and components interact, the [Power up your robot projects](/blog/power.html) post covers batteries, voltage levels, and why getting the numbers right matters for your whole build.

For a handy reference you can keep on the workbench, the [Robot Makers Almanac](/blog/robot-makers-almanac.html) has resistor colour codes, common values, and the Ohm's Law formula all in one place.

Once you're confident with fixed resistors, explore [reed switches](/blog/reed-switches.html) — they pair with a pull-up resistor to give your robot a simple magnetic sensor with just two components and three wires.
