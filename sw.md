---
layout: ptor
title: "Sw is for Swarm Robotics — The Periodic Table of Robotics"
name: Swarm Robotics
code: Sw
number: 69
category: intelligence
description: "Dozens of simple robots, no central brain — just local rules that produce surprisingly clever group behaviour."
cover: /assets/img/ptor/og/sw.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - robotics
  - ai
  - autonomy
  - multi-robot
related:
  - au
  - nn
  - pd
  - nv
  - sm
---

Take one very simple robot. It can't do much on its own. Now add fifty more, give them all the same basic rules, and watch what happens. That's swarm robotics — and the results can be remarkable.

## What is Swarm Robotics?

Swarm robotics is the study (and practice) of building systems where many small, relatively simple robots work together to accomplish tasks that none of them could manage alone. Each robot follows a handful of local rules — move towards neighbours, avoid collisions, share a signal when you find something interesting. Nobody tells the swarm what to do as a whole. Coordinated behaviour emerges from the bottom up.

The inspiration comes from nature: ants building bridges over gaps, bees finding the best flower patch, starlings forming murmurations. Roboticists are trying to do the same thing, but with code and motors.

A typical swarm robot is small and cheap. Think a robot the size of your palm, with a distance sensor, a couple of wheels, and a way to talk to its neighbours — infrared, Bluetooth, or a simple radio link. The magic is not in the hardware; it's in the algorithm.

## Why robot builders care

Swarms are inherently resilient. Lose one robot to a flat battery or a broken wheel and the swarm keeps working — there's no single point of failure.

They also scale beautifully. Need to cover a larger area? Add more robots. No need to redesign the system.

For makers, swarm concepts are useful even with just two or three robots. Getting a pair of SMARS robots to avoid each other while exploring a room is a real swarm behaviour. A group of Pico-powered rovers sharing sensor readings over Wi-Fi is a genuine swarm system — even if it fits on a desk.

## Get started

The best way to understand swarms is to build something that moves and reacts to its environment first, then think about how two of them would interact. The [MicroPython Robotics course](/learn/micropython_robotics/01_intro.html) is a great place to start — it covers motor control and sensor reading on a Raspberry Pi Pico, giving you exactly the kind of small autonomous platform a swarm is built from.

Once you have a single robot behaving reliably, try the classic "flocking" rules from Craig Reynolds' 1986 Boids algorithm: separation (don't crowd neighbours), alignment (steer the same way as neighbours), and cohesion (move towards the average position of neighbours). Implement just those three in MicroPython and you'll see genuine emergent group movement.

The [SMARS course](/learn/smars/00_intro.html) shows you how to build a proven, printable robot chassis — build two and you have a swarm to experiment with.

For simulation, NetLogo (free, browser-based) has a built-in Flocking and Ant Colony model you can tweak without any hardware at all. It's a brilliant way to develop intuition for how local rules create global patterns before you print a fleet.

Start small, stay curious, and let the collective surprise you.
