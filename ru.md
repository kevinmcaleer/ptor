---
layout: ptor
title: "Ru is for Rust — The Periodic Table of Robotics"
name: Rust
code: Ru
number: 10
category: code
description: "A systems language that catches memory bugs at compile time, giving you C-like speed without the crashes — ideal for robot firmware."
cover: /assets/img/ptor/og/ru.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - rust
  - firmware
  - embedded
related:
  - cp
  - pi
  - mp
  - py
  - li
external_link: https://www.rust-lang.org
external_label: rust-lang.org
---

Rust promises something that sounds almost too good to be true: the raw speed of C with memory safety baked in by the compiler. For robot firmware, that's a big deal.

## What is Rust?

Rust is a compiled, statically-typed programming language designed for systems programming, first released in 2015.

The headline feature is the **ownership and borrowing system**. Instead of a garbage collector slowing things down at runtime, Rust enforces strict rules at compile time about who owns a piece of memory and when it gets freed. Get it wrong and your code won't compile — which is annoying at first, but means an entire class of bugs (null pointer dereferences, buffer overflows, use-after-free) simply can't make it into your binary.

A few things worth knowing:
- Rust compiles to native machine code — no virtual machine, no interpreter.
- It targets `no_std` environments, meaning you can run it on bare-metal microcontrollers with no operating system.
- The `cargo` build tool and package manager are excellent and come bundled with the language.
- The ARM Cortex-M core inside the Raspberry Pi Pico is a supported target (`thumbv6m-none-eabi`).

## Why robot builders care

When your robot is reacting to sensor data in real time, predictable performance matters. Rust gives you deterministic execution — there's no garbage collector pausing your control loop at an inconvenient moment.

More practically: if you're writing firmware for a motor controller, a PID loop, or anything that handles interrupts close to the metal, Rust lets you write that code safely. You get the control of C without the hours of debugging mysterious memory corruption.

It also plays well with existing ecosystems. You can call C libraries from Rust (and vice versa), so you're not starting from scratch if you need a vendor's driver.

For larger projects running on Linux — a Raspberry Pi navigating a room, say — Rust's async and concurrency support means you can spin up multiple tasks without worrying about data races. The compiler catches those too.

## Get started

The best place to begin is the official toolchain installer at [rustup.rs](https://rustup.rs/), which sets up `cargo` and `rustc` in one go.

Once you're comfortable with the basics, try getting Rust running on a Raspberry Pi Pico. Kevin's [Introduction to Rust](/learn/rust/01_intro.html) course walks you through the language fundamentals, ownership and borrowing, structs, error handling, and concurrency — and it ends with a dedicated lesson on targeting the Pico directly, including cross-compiling with `cargo build --target thumbv6m-none-eabi` and flashing the resulting binary via UF2.

If you're coming from Python or MicroPython, the early lessons are designed with you in mind — the course explicitly maps Rust concepts onto things you already know from Python.

A good first mini-project: write a Rust blink program for the Pico. It covers toolchain setup, the build process, and gives you a working embedded Rust binary in under an hour.
