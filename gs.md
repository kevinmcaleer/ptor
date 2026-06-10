---
layout: ptor
title: "Gs is for GPS — The Periodic Table of Robotics"
name: GPS
code: Gs
number: 36
category: sensors
description: "GPS tells your robot exactly where it is on Earth — latitude, longitude, and altitude, updated multiple times per second, without any extra infrastructure."
cover: /assets/img/ptor/og/gs.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - gps
  - sensors
  - navigation
  - outdoor
related:
  - nv
  - sl
  - im
  - rv
  - au
---

Step outside with a GPS-equipped robot and it suddenly knows where it is on the entire planet — a remarkable thing to hand to a maker for a few pounds.

## What is GPS?

GPS — the Global Positioning System — is a network of satellites orbiting about 20,200 km above Earth. Your robot's GPS module listens to at least four of those satellites at once and uses the tiny timing differences between their signals to calculate its position — a process called trilateration.

The result is a stream of NMEA sentences: small text messages arriving over a serial (UART) connection, containing latitude, longitude, altitude, speed, heading, and satellites in view. A common module like the u-blox NEO-6M outputs these at 1–10 Hz — plenty for an outdoor rover.

Accuracy depends on conditions: a clear sky view gives you 2–5 metres, while tree cover or tall buildings can degrade that to tens of metres. For a garden rover that is usually fine; for centimetre-level work you need RTK GPS, which corrects the signal in real time.

The modules are cheap, too. A NEO-6M breakout costs under £10, connects via UART, runs on 3.3 V or 5 V, and comes with a small patch antenna.

## Why robot builders care

Knowing your position unlocks an entirely different category of robot behaviour.

- **Waypoint navigation** — give your rover a list of coordinates and it can drive to each one in turn.
- **Return-to-home** — store the starting position at boot, and the robot can always find its way back.
- **Drone flight control** — virtually every autopilot (ArduPilot, PX4) uses GPS for position hold and autonomous missions.

GPS does not work indoors and it drifts over short distances. For indoor autonomy or fine manoeuvring, you pair it with an IMU, wheel encoders, or SLAM. Outdoors, though, GPS is the sensor that turns a simple wheeled robot into something that can genuinely explore.

## Get started

The simplest first project is a GPS data reader. Connect a NEO-6M to your Pi's UART pins (or a Pico via `machine.UART`) and parse the NMEA sentences — the `micropyGPS` library handles that for you, and within a few lines of code you are printing live coordinates to the REPL.

From there, log coordinates to a CSV file as you walk around outside, then plot the track in Google My Maps — you will see the accuracy straight away.

When you are ready for a proper outdoor robot, [Rover the Mecanum Robot](/blog/Rover-mecanum.html) is a good chassis to start from — add a GPS module and a compass for heading, and you have the core of a waypoint follower.

To go further into autonomous navigation, the [Viam SLAM](/blog/viam-slam.html) article shows how a Raspberry Pi-powered robot can map its environment — skills that pair naturally with GPS outdoors.

One practical tip: give the module a clear view of the sky and wait for a good fix before moving — cold starts can take 30–60 seconds.
