---
layout: ptor
title: "Py is for Python — The Periodic Table of Robotics"
name: Python
code: Py
number: 5
category: code
description: "The friendliest language in robotics — readable, powerful, and at home on everything from a Raspberry Pi to a supercomputer."
cover: /assets/img/ptor/og/py.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - python
  - programming
  - code
  - software
related:
  - mp
  - rp
  - ai
  - ml
  - ro
external_link: https://www.python.org
external_label: python.org
---

Python is the go-to language for robotics, AI, and rapid prototyping — and once you've tried it, it's easy to see why.

## What is Python?

Python is a general-purpose, high-level programming language first released in 1991 by Guido van Rossum. It's designed to be readable: code looks almost like plain English, which means you spend less time wrestling with syntax and more time actually building things.

It runs on virtually everything. On a full Linux machine like a Raspberry Pi, Python gives you access to GPIO pins, cameras, I2C sensors, web APIs, and machine learning libraries all from one language.

Python is interpreted, so there's no compile step — write a line, run it, see what happens. That tight feedback loop makes it ideal for experimenting with sensor data, tuning a PID loop, or hacking together a new robot feature on a Saturday afternoon.

## Why robot builders care

When you're building a robot, you often need to talk to hardware, process sensor data, and make decisions — all at once. Python's ecosystem makes this surprisingly straightforward:

- **GPIO and hardware** — Libraries like `RPi.GPIO` and `gpiozero` let you control motors, LEDs, and servos with just a few lines.
- **Computer vision** — OpenCV has a first-class Python API. Reading a camera feed and detecting objects can take under 20 lines.
- **Machine learning** — TensorFlow, PyTorch, and scikit-learn all speak Python. Running a trained model on a Raspberry Pi 5 is genuinely possible.
- **ROS 2** — The dominant robotics middleware uses Python as a primary language for writing nodes and processing topics.

The only trade-off is speed. Python is slower than C++ for raw computation, which is why the heavy lifting in OpenCV and NumPy is handled by compiled C code underneath. For most robot logic — navigation decisions, state machines, sequencing — Python is plenty fast enough.

## Get started

The best first step is to get Python running on a Raspberry Pi and blink an LED. From there, you're already talking to hardware. Kevin's [Python for Beginners course](/learn/python/01_intro.html) takes you from zero to confident with the language — covering variables, loops, functions, and classes in a practical, maker-friendly way.

Once you're comfortable with the basics, [Build your own AI Assistant in Python](/blog/python-ai.html) is a great project that shows how far Python can take you — from a few lines of code to a talking, thinking assistant.

If you're working on a microcontroller like the Raspberry Pi Pico rather than a full Linux board, take a look at MicroPython (element **Mp**) — it's a lean version of Python built to run on microcontrollers, and the skills transfer almost perfectly.

Python rewards curiosity. Start small, break things, fix them, and you'll be surprised how quickly you go from "Hello, World!" to a robot that can navigate a room on its own.
