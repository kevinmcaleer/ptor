---
layout: ptor
title: "Ai is for Artificial Intelligence — The Periodic Table of Robotics"
name: Artificial Intelligence
code: Ai
number: 2
category: intelligence
description: "Give your robot the smarts to perceive its world, make decisions, and act — no human hand-holding required."
cover: /assets/img/ptor/og/ai.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - ai
  - machine learning
  - computer vision
  - neural networks
related:
  - ml
  - cv
  - nn
  - lm
  - ro
---

Intelligence is what turns a machine into a robot. The moment your creation can look at the world, decide what to do, and act on that decision — that's AI at work.

## What is Artificial Intelligence?

Artificial Intelligence is the broad field of making computers (and robots) behave in ways we'd normally call "smart". In practice, for robot builders, that breaks into a few concrete areas:

- **Computer vision** — recognising objects, faces, or lines in a camera feed
- **Machine learning** — training a model on examples so it can classify or predict new ones
- **Large Language Models (LLMs)** — using conversational AI to give your robot a voice and some reasoning ability
- **Rule-based systems** — simpler logic trees that still count as AI in many robotics contexts

You don't need a PhD. Modern tools have brought real AI within reach of a Raspberry Pi on your workbench.

## Why robot builders care

A robot without intelligence is just a remote-control toy. Add AI and things get interesting. Your wheeled rover can stop before it falls off a table (object detection). Your robotic arm can sort components by colour (computer vision + classification). Your desktop companion can hold a conversation (LLMs running locally).

Edge AI hardware — like the Raspberry Pi AI Camera with its built-in neural processing unit — means you can run object detection models in real time without a cloud subscription or a beefy GPU. That changes what a hobbyist with a Pi and a weekend can actually build.

## Get started

The best way in is to pick one slice of AI and build something with it rather than trying to learn the whole field at once.

**Computer vision** is the most immediately visual (pun very much intended). Kevin's [Computer Vision on Raspberry Pi with CVZone](/learn/cvzone/00_intro.html) course gets you from a raw camera feed to detecting and tracking objects in Python with surprisingly little code.

Ready to go deeper? The [Building Object Detection Models with Raspberry Pi AI Camera](/learn/object_model/00_intro.html) course walks you all the way from collecting your own dataset through training a PyTorch model to running it live on Pi hardware.

If LLMs are your angle, the blog post [Ollama — local ChatGPT on Pi 5](/blog/ollama.html) shows you how to run a private language model entirely on a Raspberry Pi 5 — no internet required, no API key, no monthly bill.

Start with one project. Get it working. Then follow your curiosity — the field is enormous, and every direction is worth exploring.
