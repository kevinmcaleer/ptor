---
layout: ptor
title: "Pe is for Pet Robots — The Periodic Table of Robotics"
name: Pet Robots
code: Pe
number: 83
category: robots
description: "Robots with personality — build a four-legged companion, a curious owl, or a bunny that wags its ears on command."
cover: /assets/img/ptor/og/pe.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - pets
  - robot
  - companion
  - animatronic
related:
  - qd
  - sv
  - pc
  - sm
  - hu
---

There's something different about building a robot that feels alive. Pet robots aren't just machines — they're characters. Give a robot a name, a waggy tail, or a blinking eye, and suddenly everyone in the room wants to say hello to it.

## What is a Pet Robot?

A pet robot is any robot designed to behave like an animal companion — dogs, cats, birds, bunnies, or creatures entirely from your imagination. The defining feature isn't the shape; it's the personality. Pet robots move in ways that feel expressive. They respond to touch or sound. They have idle animations, moods, and a habit of making people smile.

Famous examples range from Sony's AIBO to Boston Dynamics' Spot, but you don't need a corporate budget. The maker community has produced brilliant open designs — four-legged walkers powered by a Raspberry Pi Pico, steampunk owls that react to gestures, even Easter bunnies with servo-driven ears.

## Why robot builders care

Pet robots are a brilliant learning project because they combine almost every robotics skill at once:

- **Servos** — most pet robots are driven entirely by hobby servos, so you'll learn inverse kinematics and gait patterns hands-on.
- **Personality through code** — idle behaviours, random head tilts, and reaction animations are all just if-statements and timers, but the effect is magical.
- **3D printing** — a custom body transforms a pile of PCBs and servos into something with real character.
- **Sensors** — add an ultrasonic sensor or a camera and your pet can "notice" things in its environment.

The feedback loop is instant and motivating. When your four-legged bot takes its first wobbly steps, it feels like a small miracle.

## Get started

The best first pet robot for most makers is a quadruped — four legs, eight servos, and endless room to grow. Kevin's [SMARS Quad course](/learn/smars_quad/00_intro.html) walks you through building and programming a four-legged SMARS robot from scratch, covering gait sequences and MicroPython control.

If you want something a little more exotic, take a look at [PicoCat v2](/blog/picocat-v2.html) — a Raspberry Pi Pico–powered robot cat with a 3D-printed body and smooth servo movements. The [Bugs the Robo-Bunny build blog](/blog/robobunny.html) shows how the same PicoCat platform can become a completely different character with a new body design.

For a companion bot with real presence, [Bubo-2T](/blog/bubo-2t.html) is a steampunk owl that reacts to hand gestures and even posts to Mastodon — proof that pet robots can have genuinely useful (and deeply weird) personalities.

Start simple: pick one animal, sketch its shape, decide on four to eight servos, and write a single idle animation. Once it does one thing that looks alive, you won't be able to stop.
