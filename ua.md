---
layout: ptor
title: "Ua is for UART — The Periodic Table of Robotics"
name: UART
code: Ua
number: 41
category: signals
description: "Two wires, two directions, one rock-solid link — UART is the classic serial protocol that powers debugging, GPS, and more."
cover: /assets/img/ptor/og/ua.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - electronics
  - micropython
  - serial
  - communication
related:
  - i2
  - sp
  - io
  - mp
  - pi
---

UART has been around since the dawn of microcontrollers, and it's still one of the first things you reach for when you want two devices to talk. Two wires, a shared baud rate, and you're off.

## What is UART?

UART stands for **Universal Asynchronous Receiver-Transmitter**. It's a hardware serial communication protocol that sends data one bit at a time over two lines: **TX** (transmit) and **RX** (receive). Cross them over between devices — your TX connects to their RX, and vice versa — and they can exchange data in both directions.

The "asynchronous" part means there's no shared clock signal. Instead, both sides agree on a **baud rate** — the speed in bits per second. Common rates are 9600, 115200, and 921600 baud. Get the baud rate wrong and you'll get garbled nonsense; get it right and data flows cleanly.

A typical UART frame is just a start bit, eight data bits, and a stop bit. That's it. Beautifully simple.

## The crossover wiring

The one rule that trips everyone up: **TX connects to RX, not TX to TX**. Each device's transmit line feeds the other's receive line, and they must share a common ground:

```
      Device A                     Device B
   ┌───────────┐                ┌───────────┐
   │       TX ─┼────────────────┼─▶ RX      │
   │       RX ◀┼────────────────┼─ TX       │
   │      GND ─┼────────────────┼─ GND      │
   └───────────┘                └───────────┘
        TX → RX (crossed),  GND → GND (common)
```

## One byte on the wire

With no shared clock, both sides must agree on the **baud rate** in advance. The line idles HIGH, a single LOW **start bit** wakes the receiver, then 8 data bits follow, finished by a HIGH **stop bit**:

```
   idle  start │  8 data bits (LSB first)  │ stop  idle
   ────┐       ┌───┐   ┌───┐       ┌───────┐       ┌────
       │       │ 0 │ 1 │ 0 │ 1 1 0 │ 1   1 │       │
       └───────┘   └───┘   └───────┘       └───────┘
        ↑start                              ↑stop
        bit                                 bit
```

Get the baud rate wrong and the receiver samples at the wrong moments — that's why a mismatched setup gives you garbled characters rather than silence.

## Why robot builders care

UART is everywhere in robotics. GPS modules, GSM shields, LiDAR sensors, servo driver boards — a huge number of peripherals speak UART because it needs so few pins and works reliably over short cable runs.

It's also your best friend for **debugging**. When your robot is misbehaving and you can't work out why, printing messages over UART to a serial terminal tells you exactly what's happening inside. On MicroPython, `print()` goes straight to the REPL over USB-serial — that's UART under the hood.

Bus servos are a great modern example. The [Feetech STS3215 and similar bus servos](/blog/bus-servos.html) use half-duplex UART — a single wire handles both TX and RX — to daisy-chain multiple servos on one connection. Each servo has an ID, so the controller can address them individually.

## Get started

The Raspberry Pi Pico has two hardware UART peripherals, `UART0` and `UART1`, available on several pin pairs. Here's the simplest MicroPython setup:

```python
from machine import UART, Pin

uart = UART(0, baudrate=9600, tx=Pin(0), rx=Pin(1))
uart.write("Hello from UART!\n")

if uart.any():
    print(uart.read())
```

Pick a baud rate, hook up TX-to-RX and RX-to-TX, share a common ground, and start sending.

A solid first project is to wire up a cheap UART GPS module (like the NEO-6M) to your Pico. At 9600 baud it streams NMEA sentences — strings of text containing your position, speed, and time. Parse those and you've got a GPS robot on your hands.

For a broader grounding, the [Talking to the World — Working with I2C and SPI](/learn/i2c_spi/00_intro.html) course covers the neighbouring protocols in detail — understanding all three helps you pick the right bus for the job. And if MicroPython is new to you, [Learn MicroPython — the basics](/learn/micropython/00_intro.html) is the place to start before diving into hardware communication.

Once you're comfortable with basic UART, explore half-duplex setups for bus servos, or try logging sensor data to a PC in real time. UART keeps popping up no matter where you look in robotics.
