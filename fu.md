---
layout: ptor
title: "Fu is for Fusion 360 — The Periodic Table of Robotics"
name: Fusion 360
code: Fu
number: 59
category: making
description: "Autodesk's professional parametric CAD tool, free for personal makers — design robot parts with precision and print them the same day."
cover: /assets/img/ptor/og/fu.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - fusion_360
  - 3ddesign
  - cad
  - 3d_printing
related:
  - cd
  - pr
  - fc
  - ch
  - gr
external_link: https://www.autodesk.com/products/fusion-360/personal
external_label: Fusion 360 Personal
---

Fusion 360 is the CAD tool that turns your robot ideas into printable parts. If you've ever sketched a bracket on a notepad and wondered how to make it real, this is where the magic happens.

## What is Fusion 360?

Fusion 360 is a professional-grade parametric CAD, CAM, and electronics design application made by Autodesk. "Parametric" means every dimension is driven by a number you can change — tweak the hole diameter and the surrounding geometry updates automatically. It runs on Windows and macOS, and Autodesk offers a free Personal Use licence for hobbyists and makers, which covers almost everything you'll need for robot building.

The workflow is straightforward: you create 2D sketches, extrude or revolve them into 3D bodies, and then assemble multiple components together. When everything looks right, you export an STL and send it to your printer.

## Why robot builders care

Most robot parts need to fit together precisely. A motor mount that's 0.5 mm off will cause your chassis to rack and bind. Fusion 360 lets you model to exact tolerances, measure clearances inside the assembly, and iterate quickly — change one number, regenerate, re-export, and print again.

You can also model gears, threads, and living hinges that would be near-impossible to draw freehand. The Timeline feature (that row of icons at the bottom of the screen) records every modelling step, so you can roll back a mistake without starting from scratch. And because Fusion stores your designs in the cloud, you can pick up on any machine.

For robot builders specifically, Fusion 360 shines when you're designing custom chassis, brackets, servo horns, and enclosures — all the bespoke parts that don't exist off the shelf.

## Get started

Download the free Personal licence from the Autodesk site linked above. The learning curve is real but shorter than it looks — spend an hour on the official tutorials and you'll be extruding your first sketch by lunchtime.

Once you're comfortable with basic modelling, try designing a real robot component. Kevin's course [Build a SMARS Robot in Fusion 360](/learn/smars_fusion360/00_intro.html) walks you through designing the classic SMARS wheeled robot from scratch, covering sketches, extrusions, and assembly — a great first project because the geometry is simple but the result is immediately printable and useful.

When you want to go further, Kevin's post on [Creating Gears in Fusion 360](/blog/creating-gears-in-fusion-360.html) shows how to use the built-in gear generator to produce meshing spur gears for your drivetrain — one of the most satisfying things you can do in CAD.

A good early habit: model your electronics (motor, Pico, battery pack) as simple box placeholders inside your assembly. That way you catch interference problems before you've wasted filament.
