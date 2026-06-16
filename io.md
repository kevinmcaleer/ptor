---
layout: ptor
title: "Io is for GPIO — The Periodic Table of Robotics"
name: GPIO
code: Io
number: 26
category: signals
description: "GPIO pins are where your code steps off the screen and into the real world — controlling motors, reading sensors, and bringing robots to life."
cover: /assets/img/ptor/og/io.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - pico
  - micropython
  - raspberry pi
  - electronics
  - sensors
related:
  - pw
  - i2
  - sp
  - ua
  - pi
---

Pick up a Raspberry Pi Pico or an ESP32 and you will find a row of little numbered pins around the edge. Those are GPIO pins — and they are the reason your code can make things happen in the physical world.

## What is GPIO?

GPIO stands for General-Purpose Input/Output. Each pin on a microcontroller or single-board computer can be set up, in software, to either read a signal coming in (input) or send a signal going out (output).

In output mode a pin can switch an LED on and off, drive a buzzer, or tell a motor driver to spin a wheel. In input mode the same pin can detect a button press, read a switch, or receive a signal from a sensor.

Pins are digital by default — they deal in two states: HIGH (usually 3.3 V) and LOW (0 V). Many boards also have pins that can read analogue voltages using an analogue-to-digital converter (ADC), which turns a smoothly varying voltage into a number your code can work with.

## Input and output

The same pin can do two opposite jobs depending on how your code configures it. As an **output** it pushes voltage out to drive something; as an **input** it reads voltage coming in. Here are the two everyday wiring patterns — an LED on an output and a button on an input:

```
   OUTPUT — drive an LED            INPUT — read a button

   GPIO ──[220Ω]──▶|── GND          3.3V ──[10kΩ]──┬── GPIO
                   LED                              │
                                                  [BTN]
   pin HIGH → LED on                                │
   pin LOW  → LED off                              GND

                                    not pressed → reads HIGH
                                    pressed     → reads LOW
```

The 10 kΩ resistor on the button is a **pull-up**: it holds the pin at a known HIGH until the button connects it to ground. Without it the pin "floats" and reads random noise — a classic beginner gotcha.

## Why robot builders care

GPIO is the connection point between your software and everything physical. Without it, a robot is just a piece of code sitting idle.

- **Sensors** — ultrasonic rangefinders, infrared sensors, and temperature modules all talk to your microcontroller through GPIO pins.
- **Actuators** — motor drivers, servos, and LEDs all take their orders from GPIO signals.
- **Feedback loops** — reading a sensor on an input pin and reacting on an output pin is the foundation of every autonomous behaviour.
- **Protocols built on GPIO** — I2C, SPI, and UART are all implemented on top of dedicated GPIO lines. Understanding plain GPIO first makes those protocols far less mysterious.

## Get started

The classic first GPIO project is a blinking LED — an output pin switches an LED on and off in a loop. From there, add a button on an input pin and you have got user interaction. It sounds simple, but this two-pin circuit is the kernel of a robot's control loop.

The [Raspberry Pi Pico with MicroPython — GPIO Mastery](/learn/micropython_gpio/00_intro.html) course covers everything from pin modes and pull-up resistors to reading analogue sensors and driving outputs. It is the most direct path from "what is a GPIO pin?" to confidently wiring up real hardware.

When you are ready for a practical project, the [Hacky Temperature and Humidity Sensor](/blog/hacky-sensor.html) is a great low-cost build that reads a DHT22 sensor through a single GPIO pin on a Pico. It proves the point quickly — a few lines of MicroPython, one pin, and you are logging real environmental data.

If you want to explore more input types, the [Reed Switches](/blog/reed-switches.html) post shows how magnetic switches wire into GPIO input pins.

One practical tip: always check your microcontroller's pin voltage. Most GPIO pins operate at 3.3 V. Connecting a 5 V sensor directly can damage the pin permanently — use a voltage divider or a level shifter.
