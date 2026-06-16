---
layout: ptor
title: "Im is for IMU — The Periodic Table of Robotics"
name: IMU
code: Im
number: 35
category: sensors
description: "Give your robot a sense of balance and direction — an IMU measures tilt, rotation, and acceleration so it always knows which way is up."
cover: /assets/img/ptor/og/im.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - sensors
  - micropython
  - i2c
  - motion
related:
  - pd
  - i2
  - sl
  - qd
  - us
---

Your robot can't feel the floor shifting beneath it. Without an IMU, it has no idea whether it's level, tilting sideways, or spinning on the spot. Add one, and suddenly it has a sense of its own body in space.

## What is an IMU?

An **Inertial Measurement Unit** (IMU) is a small chip that combines two or three sensors in one package:

- **Accelerometer** — measures linear acceleration along X, Y, and Z axes (in m/s² or g). At rest on a flat surface, it reads 1g downward, which tells you the direction of gravity — and therefore which way is up.
- **Gyroscope** — measures rotational velocity (degrees per second). It tracks how fast the robot is turning around each axis.
- **Magnetometer** (on 9-DOF variants) — acts like a digital compass, giving absolute heading relative to magnetic north.

The most common hobby IMUs are the **MPU-6050** (6-axis, around £1–£2) and the **BNO055** (9-axis with onboard fusion processor). Both communicate over **I2C**, which means you only need two wires to connect one to a Raspberry Pi Pico or Arduino.

## The three axes

Every reading the IMU gives you is measured along (or around) three axes. The accelerometer measures *acceleration along* X, Y and Z; the gyroscope measures *rotation around* them — often called roll, pitch and yaw:

```
              Z (up)
              │
              │        Yaw   = rotation around Z (turning left/right)
              │        Pitch = rotation around Y (nose up/down)
              │        Roll  = rotation around X (tilting sideways)
              │
              └─────────── Y
             ╱
            ╱
           X  (forward)

   At rest, the Z accelerometer reads ~1 g — that's
   gravity, and it tells the robot which way is "up".
```

The accelerometer is steady but noisy; the gyro is smooth but drifts over time. Blend them with a complementary or Kalman filter and you get an angle that's both stable and drift-free.

Raw accelerometer data is noisy and raw gyro data drifts over time. In practice you combine both using a **complementary filter** or a **Kalman filter** to get smooth, reliable angle readings — the filter blends the gyro's short-term precision with the accelerometer's long-term accuracy.

## Why robot builders care

An IMU unlocks a whole class of robot behaviour that's simply impossible without one:

- **Self-balancing robots** — a two-wheeled balancing bot (think Segway-style) relies entirely on a fast IMU loop to stay upright. If the pitch angle tips beyond a threshold, the motors correct.
- **Quadrupeds and hexapods** — knowing body tilt helps the robot adjust leg positions to stay stable on uneven ground.
- **Dead reckoning** — integrate acceleration over time to estimate how far and in which direction the robot has moved (useful when GPS isn't available indoors).
- **Drone stabilisation** — every flight controller uses an IMU as its primary feedback sensor.

## Get started

The **MPU-6050** is the classic first IMU. It costs almost nothing, runs on 3.3 V or 5 V, and has a good MicroPython library. Wire SDA and SCL to your Pico's I2C pins, supply 3.3 V, and you're reading accelerometer data in a dozen lines of code.

The [Talking to the World — Working with I2C and SPI](/learn/i2c_spi/00_intro.html) course is the ideal companion here. It covers scanning the I2C bus to find your sensor's address, reading raw bytes from registers, and converting them to useful values — exactly the skills you need to bring an IMU to life.

For a complete robot project that makes real use of motion sensing, the [MicroPython Robotics Projects](/learn/micropython_robotics/01_intro.html) course shows how sensor data feeds into robot decision-making on a Pico-based build.

Once you're comfortable reading raw values, the natural next step is a simple complementary filter — blend the gyro and accelerometer readings and you'll have smooth, drift-free angles within an afternoon.
