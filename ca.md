---
layout: ptor
title: "Ca is for Capacitors — The Periodic Table of Robotics"
name: Capacitors
code: Ca
number: 20
category: foundations
description: "Tiny components that store and release charge — essential for smoothing power and protecting your circuits from voltage spikes."
cover: /assets/img/ptor/og/ca.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - circuits
  - power
related:
  - re
  - tr
  - oh
  - ba
  - pb
---

Capacitors are small but they pull serious weight in any robot build. Get them wrong — or leave them out — and your robot can glitch, reset, or damage its own components.

## What is a Capacitor?

A capacitor stores electrical charge between two conductive plates separated by an insulator (called a dielectric). When voltage rises, it stores charge. When voltage dips, it releases that charge back into the circuit.

The amount of charge it can hold is called **capacitance**, measured in **farads (F)**. Most capacitors you'll use are tiny fractions of a farad — microfarads (µF), nanofarads (nF), or picofarads (pF).

There are two main types to know:

- **Electrolytic capacitors** — larger values (1µF to thousands of µF), cylindrical, and polarised (the negative leg must connect to GND). Great for power smoothing.
- **Ceramic capacitors** — small values (10pF to 100nF), disc-shaped, not polarised. Used everywhere as decoupling caps.

Supercapacitors (or "ultracapacitors") take things further still — they can store enough energy to act as a short-term backup power source for a robot.

## The symbol and pins

Capacitors come in two flavours on a schematic. A ceramic (non-polarised) cap is two straight plates — it goes in either way round. An electrolytic cap has one curved plate marking the negative side, and that pin **must** go to the more negative point in your circuit or it can fail (sometimes spectacularly):

```
  Ceramic (non-polarised)        Electrolytic (polarised)

      |   |                            +  |  )
  ----+   +----                    -------+  )-------
      |   |                            -  |  )
   either way round              + leg long, - leg has
                                  the stripe on the body
```

The longer leg on an electrolytic is the **positive (+)** terminal; the shorter leg, marked with a stripe down the side of the can, is the **negative (−)** terminal.

## In a circuit

The two jobs you'll use most: a decoupling cap sitting right across a chip's power pins, and a smoothing cap across a motor to soak up its electrical noise before it reaches your microcontroller:

```mermaid
flowchart LR
    VCC["VCC (+)"] --> CHIP["Microcontroller"]
    CHIP --> GND["GND (−)"]
    VCC -.->|"100 nF<br/>decoupling cap"| GND
    BATT["Battery +"] --> MOTOR["DC Motor"]
    MOTOR --> BGND["Battery −"]
    MOTOR -.->|"100 nF across<br/>motor terminals"| MOTOR
```

Keep decoupling caps as close to the chip's power pin as possible — the shorter the leads, the better they smooth out the rapid current spikes a busy microcontroller creates.

## Why robot builders care

Motors are electrically noisy. Every time a DC motor starts, stops, or changes speed, it creates a voltage spike that can crash your microcontroller or corrupt sensor readings. A capacitor placed across the motor terminals absorbs that spike before it travels up the power rail.

Microcontrollers and sensors also have a trick called **decoupling**: a small ceramic capacitor (typically 100nF) placed right next to each chip's power pin acts as a tiny local reservoir, keeping the voltage steady during rapid switching. The [I2C and SPI course](/learn/i2c_spi/00_intro.html) goes into this in detail — it's one of the first fixes when sensor readings go flaky.

Power rails with batteries benefit from a larger electrolytic cap too. It smooths out the sag you get when a servo lurches into position — exactly the kind of scenario covered in the [Power up your robot projects](/blog/power.html) guide.

## Get started

The easiest first experiment is a **motor decoupling cap**. Grab a DC motor, a AA battery pack, and a 100nF ceramic capacitor. Solder the cap directly across the motor's two terminals (polarity doesn't matter for ceramic caps). Now connect the motor. You've just built your first noise filter.

Next, grab three 100nF ceramic caps and drop one across the VCC and GND pins of each IC on a breadboard project. This one habit will save you hours of mysterious debugging later.

When your projects grow to include multiple servos or larger motors, a 100–470µF electrolytic cap across the power rail will prevent resets. Just check the polarity stripe — the negative side goes to ground, every time.
