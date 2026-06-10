---
layout: ptor
title: "Wh is for Wheels — The Periodic Table of Robotics"
name: Wheels
code: Wh
number: 48
category: making
description: "Wheels are where power meets the ground — pick the right type and your robot moves smoothly, quickly, and exactly where you point it."
cover: /assets/img/ptor/og/wh.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - robot
  - 3d_printing
  - locomotion
  - chassis
related:
  - dc
  - ch
  - hb
  - tk
  - pr
---

Thousands of years after someone first rolled a log under a heavy stone, wheels are still the most practical way to get a robot from A to B. Simple, efficient, and surprisingly nuanced once you start thinking about grip, diameter, and omni-directional movement.

## What is a Wheel?

In robotics, a wheel is a round rolling element attached to a motor shaft that converts rotational motion into linear travel. That sounds obvious — but the *type* of wheel matters enormously.

Common wheel styles for robot builders:

- **Rubber-tyred wheels** — grippy, cheap, great on smooth floors. The yellow TT motor wheel is the classic beginner choice.
- **Omni wheels** — a ring of small passive rollers around the rim lets the wheel slide sideways. Two or three of these let a robot spin in place or strafe.
- **Mecanum wheels** — rollers set at 45° give full holonomic movement: forwards, sideways, and diagonal without turning the chassis.
- **3D-printed wheels** — customisable diameter, tread pattern, and hub style. Perfect for matching a specific motor shaft size or achieving a particular aesthetic.

Wheel diameter directly affects speed and torque. A bigger wheel covers more ground per revolution (faster) but needs more torque to get moving. A smaller wheel gives you more pushing force but lower top speed.

## Why robot builders care

Wheel choice is one of the first real design decisions you make. Get it wrong and your robot either spins on the spot (not enough grip), strains its motors (too heavy), or can't handle the surface (too small for carpet, too wide for tight corridors).

For a simple two-wheeled differential drive robot, matching wheel diameter to motor gearing gives you a predictable relationship between encoder ticks and distance travelled — essential once you start writing navigation code.

Tyre material matters too. Hard plastic slides; rubber grips. On carpet or any textured surface, you want rubber or TPU (a flexible filament) wrapped around the wheel.

## Get started

A great first project is building a two-wheeled robot with 3D-printed wheels sized to fit your motor shafts exactly. Kevin's [BurgerBot](/blog/burgerbot.html) is a brilliant starting point — it uses 3D-printed wheels on TT motors and the whole chassis is printable at home.

If you want to go further, the [SMARS](/learn/smars/00_intro.html) course shows you how to build and program a modular robot whose wheel and track options are interchangeable — swap between wheeled and tracked locomotion to see the real-world difference in grip and manoeuvrability.

For a taste of advanced wheel types, check out the [Rover the Mecanum Robot](/blog/Rover-mecanum.html) project. Mecanum wheels let Rover strafe sideways and spin on the spot — the kind of movement that makes people stop and stare.

Print a wheel, bolt it to a motor, press it to the floor, and watch it roll. That first metre of motion is the moment your robot stops being a circuit and starts being a vehicle.
