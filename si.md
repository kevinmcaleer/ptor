---
layout: ptor
title: "Si is for Simulation — The Periodic Table of Robotics"
name: Simulation
code: Si
number: 17
category: code
description: "Test your robot in a virtual world first — crash a thousand times in software before you bend a single servo in real life."
cover: /assets/img/ptor/og/si.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - simulation
  - ros
  - gazebo
  - testing
related:
  - ro
  - sl
  - pd
  - cv
  - au
external_link: https://gazebosim.org
external_label: gazebosim.org
---

Before you solder a single wire, you can build a complete robot, drop it into a virtual world, and watch it crash — safely, cheaply, and as many times as you like. That is the superpower of simulation.

## What is Simulation?

Robot simulation is the practice of running a virtual model of your robot inside a physics engine. The software calculates forces, collisions, motor torques, sensor readings, and even camera images — all without any real hardware.

Popular simulators include:

- **Gazebo** — the standard simulator for ROS projects. Full physics, sensors, and a 3D world editor. Free and open source.
- **Webots** — another open-source option, great for beginners and used widely in education.
- **NVIDIA Isaac Sim** — GPU-accelerated, photorealistic, and aimed at professional robotics teams.

A simulated robot can have the same code running on it as the real one — your navigation or arm-control code connects to virtual sensor topics just as it would on real hardware.

## Why robot builders care

Simulation saves time, money, and frustration in equal measure.

Hardware is slow to iterate. Printing a new chassis takes hours. Waiting for a part to arrive takes days. In simulation you tweak a joint angle, relaunch, and see the result in seconds.

Hardware is also unforgiving. A badly tuned PID controller can strip a servo gear. A navigation bug can send your rover off a table. In simulation, consequences are just a restart.

At a practical level, simulation lets you:

- **Test code before hardware exists** — write and debug your control logic while the robot is still being printed.
- **Try dangerous scenarios safely** — run a robot at full speed into a wall a hundred times to tune the collision response.
- **Generate training data** — ML models for vision or control need thousands of examples; a simulator can produce them overnight.
- **Replay and debug** — record a simulated run, replay it frame by frame, inspect every sensor value.

## Get started

The most accessible entry point is **Gazebo with ROS 2**. You install both, load a sample robot model (the TurtleBot 3 is the classic starter), and drive it around a virtual room using keyboard commands. No soldering required.

Kevin's [Learn ROS with me](/learn/learn_ros/00_intro.html) course walks you through setting up ROS 2 and Gazebo step by step. It covers launching a simulated robot, reading sensor topics, and building toward autonomous navigation — all in simulation first.

Once you are comfortable with the basics, the [Guiding Light](/blog/guiding-light.html) project shows how LiDAR mapping with RViz works in practice — the same visualisation tools you use with simulated sensor data carry straight over to real hardware.

A solid first mini-project: download the TurtleBot 3 simulation package, launch the house world in Gazebo, and write a simple Python node that makes the robot drive in a square. When the square looks right in simulation, your real robot should do the same — same code, different body.
