---
layout: ptor
title: "Cm is for Cameras — The Periodic Table of Robotics"
name: Cameras
code: Cm
number: 33
category: sensors
description: "Give your robot eyes — learn how cameras work with Raspberry Pi, from simple snapshots to real-time object detection and AI vision."
cover: /assets/img/ptor/og/cm.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - camera
  - computer vision
  - raspberry pi
  - opencv
related:
  - cv
  - ml
  - rp
  - ir
  - us
---

A camera turns your robot from a blind machine into one that can see the world. That single upgrade opens up a huge range of possibilities — from following a coloured ball to recognising faces to navigating a room without bumping into the furniture.

## What is a Camera (in robotics)?

In robotics, "camera" covers everything from a basic USB webcam to a dedicated board camera like the Raspberry Pi Camera Module 3. The Pi Camera connects directly to the CSI port on a Raspberry Pi, giving you full resolution control and access to features like autofocus and HDR. The newer Raspberry Pi AI Camera adds a built-in neural network accelerator (Sony IMX500 chip), letting you run object detection models right on the sensor — no extra processing needed from the Pi itself.

Resolution matters, but frame rate matters just as much for a moving robot. For most beginner projects, 1080p at 30 fps is plenty — and even 640×480 is enough for real-time colour tracking.

Libraries like OpenCV give you the tools to process what the camera captures: detect edges, find contours, track objects by colour, or feed frames into a machine-learning model. CVZone builds on top of OpenCV and makes common computer-vision tasks (hand tracking, pose estimation, face detection) accessible with just a few lines of Python.

## Why robot builders care

Vision is the richest sensor a robot can have. A single camera gives you colour, distance cues, shape recognition, and motion detection — all at once. Compare that to an ultrasonic sensor, which only tells you there's something 30 cm ahead, or an infrared sensor, which just sees a line on the floor. A camera tells you *what* is ahead, not just *that* something is there.

That richness does come at a cost: processing video in real time takes real compute, which is why the Raspberry Pi 4 or 5 is a natural pairing. For lighter tasks, an ESP32-CAM module adds basic streaming video to a tiny board for just a few pounds.

## Get started

The best way in is to build something with immediate visual feedback. Kevin's [Computer Vision on Raspberry Pi with CVZone](/learn/cvzone/00_intro.html) course starts from a basic camera feed and works up to posture detection and hand-tracking — no computer-vision background needed. If you want to go further and train your own models, [Building Object Detection Models with Raspberry Pi AI Camera](/learn/object_model/00_intro.html) covers PyTorch training and edge deployment on the AI Camera.

For inspiration on what a camera-equipped robot actually looks like as a finished project, the [PIKON Camera build](/blog/pikon-camera.html) shows a high-quality Raspberry Pi camera enclosure built from scratch — and the [Face Detection with Trilobot](/blog/face-detection-trilobot.html) post puts it all together with a robot that follows a detected face.

Start with a still image, then a live feed, then try tracking a coloured object. Each step builds confidence, and before long your robot won't just react to the world — it'll actually see it.
