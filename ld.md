---
layout: ptor
title: "Ld is for LiDAR — The Periodic Table of Robotics"
name: LiDAR
code: Ld
number: 34
category: sensors
description: "Spin a laser 360° thousands of times a second and your robot gets a live map of everything around it — no guessing required."
cover: /assets/img/ptor/og/ld.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - lidar
  - sensors
  - mapping
  - navigation
related:
  - sl
  - nv
  - ro
  - us
  - im
---

Point a laser at something and time how long the light takes to bounce back. Do that 4,000 times a second while spinning the sensor in a full circle, and suddenly your robot knows exactly where every wall, chair leg, and wandering cat is — all in real time.

## What is LiDAR?

LiDAR stands for **Light Detection and Ranging**. A small motor spins a laser emitter and receiver around a central axis, typically at 5–10 Hz (rotations per second). Each pulse of infrared light bounces off an obstacle and returns; the sensor measures the time of flight (TOF) to calculate distance.

The result is a continuous stream of distance readings arranged around a 360° ring — a **point cloud**. Affordable units like the RPLidar A1 produce 2,000–4,000 samples per rotation with a range of up to 8 metres — for a hobby robot, the cheap spinning disc does the job brilliantly.

LiDAR is unaffected by ambient light levels, which makes it far more reliable than cameras in dark or glare-heavy environments.

## Why robot builders care

A single ultrasonic sensor tells you there's something 30 cm ahead. A LiDAR tells you there are walls 28 cm ahead, 42 cm to your left, and 1.1 metres behind — all at once. That rich spatial data is what makes truly autonomous navigation possible.

With a LiDAR you can:

- Build a 2D floor plan of a room in real time (**SLAM** — Simultaneous Localisation and Mapping)
- Detect and avoid obstacles in every direction without turning the robot
- Give a path-planning algorithm the data it needs to choose routes intelligently
- Localise the robot inside a known map

LiDAR is the core sensor in most serious mobile robots, from Roombas to self-driving cars. Getting one spinning on your own build is a massive step up from bumping into walls.

## Get started

The **RPLidar A1** from Slamtec is the most popular entry-level unit. It connects via USB (or UART) and costs under £100. Pair it with a Raspberry Pi and you have everything you need to produce your first live map.

Kevin's [Guiding Light](/blog/guiding-light.html) post walks through mounting an RPLidar on a Raspberry Pi Zero 2W, installing ROS, and visualising the scan output in Rviz — a great first project that takes you from zero to spinning laser in an afternoon.

Once you've seen a live scan, the natural next step is SLAM. Kevin's [Viam SLAM](/blog/viam-slam.html) post uses the Viam robotics platform to build a full room map and navigate it autonomously, with LiDAR as the primary sensor. The [Cubie-1 robot](/blog/meet-cubie.html) uses exactly this setup, and the [LidarBot](/blog/lidarbot.html) project shows a compact Pico-based build that uses LiDAR for obstacle avoidance.

If you want to go deeper, the [Learn ROS with me](/learn/learn_ros/00_intro.html) course covers the full software stack around LiDAR data — scan topics, transforms, and the nav stack that turns raw distance readings into a robot that can find its own way home.
