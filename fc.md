---
layout: ptor
title: "Fc is for FreeCAD — The Periodic Table of Robotics"
name: FreeCAD
code: Fc
number: 60
category: making
description: "Design every part of your robot from scratch with this powerful, fully open-source parametric CAD tool — no subscription, no strings."
cover: /assets/img/ptor/og/fc.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - freecad
  - 3ddesign
  - cad
  - 3dprinting
related:
  - pr
  - cd
  - ch
  - sm
  - lc
external_link: https://www.freecad.org
external_label: freecad.org
---

You want to design a custom robot chassis, a bracket that fits your exact servo, or a wheel with the right diameter for your build. FreeCAD lets you do all of that — for free, forever, on any operating system.

## What is FreeCAD?

FreeCAD is a free, open-source parametric 3D CAD application. Parametric means your dimensions are stored as editable numbers, not baked-in geometry. Change a value in a spreadsheet and the whole model updates in one go — perfect for iterating robot parts where a single measurement rarely stays fixed.

It runs on Windows, macOS, and Linux. It exports to STL for 3D printing, STEP for sharing with other CAD tools, and DXF for laser cutters. You own your files completely; there is no cloud lock-in, no licence server, no subscription that expires.

Key features useful to robot builders:

- **Part Design workbench** — sketch a 2D profile, extrude or revolve it into a solid, add fillets and chamfers.
- **Sketcher** — constrain geometry with dimensions and relationships so parts stay consistent when you iterate.
- **Spreadsheet-driven design** — store all your key measurements in one place and reference them across parts.

Version 1.0 of FreeCAD arrived in late 2024, a significant milestone that brought a much-improved topological naming fix — a long-standing source of frustration for new users. If you tried FreeCAD years ago and found it maddening, it is worth another look.

## Why robot builders care

Commercial CAD tools like Fusion 360 have free tiers with restrictions. FreeCAD has no tier. You get everything: unlimited parts, unlimited exports, full scripting via Python, and a community that has been building open tutorials for over a decade.

For robot builders specifically, parametric design pays dividends. You model a wheel hub at 30 mm diameter. The motor shaft turns out to be 5 mm wide instead of 4 mm — edit one number, regenerate, re-export, re-print. No redrawing from scratch.


## Get started

The best place to begin on kevsrobots.com is the [Introduction to FreeCAD for Beginners](/learn/freecad/01_introduction_to_freecad.html) course. It walks you through installing FreeCAD, navigating the interface, and creating your first sketch and solid — the core loop you will repeat for every single part you design.

Once you have the basics, the [Building SMARS with FreeCAD](/learn/freecad_smars/00_intro.html) course is a brilliant next step. You design a complete 3D-printable robot chassis from scratch using parametric techniques — real robot geometry, not just practice boxes. By the end you have a set of print-ready files and a solid understanding of how to approach any future robot design.

A good first mini-project: model a simple servo bracket. Measure your servo's body dimensions, sketch the outline in the Sketcher workbench, extrude it to thickness, and add mounting holes. Print it, test the fit, adjust the numbers, reprint. That loop — measure, model, print, fit — is the core skill of every robot builder who makes their own parts.
