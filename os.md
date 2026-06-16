---
layout: ptor
title: "Os is for Open Source — The Periodic Table of Robotics"
name: Open Source
code: Os
number: 18
category: code
description: "Shared designs, code and firmware that anyone can use, remix and improve — the foundation that makes hobby robotics affordable and fast to learn."
cover: /assets/img/ptor/og/os.png
author: Kevin McAleer
date: 2026-06-10
tags:
  - open source
  - software
  - community
  - github
related:
  - gi
  - li
  - mp
  - sm
  - fc
external_link: https://opensource.org/licenses
external_label: Open Source Licences
---

Without open source, hobby robotics would cost ten times as much and take ten times as long. It really is that simple.

## What is Open Source?

Open source means the source — code, schematics, firmware, 3D model files — is published under a licence that lets anyone read it, copy it, modify it and redistribute it. The exact rules vary by licence (MIT, GPL, Creative Commons and so on), but the core principle is the same: no one locks the knowledge away.

In robotics this applies to almost every layer of your build. MicroPython is open source. FreeCAD is open source. Arduino's IDE and its entire library ecosystem are open source. The Robot Operating System (ROS) is open source. Even many physical robot designs — chassis STL files, PCB layouts, wiring diagrams — are released openly on GitHub or Printables.

A few things worth knowing:

- **Licences matter.** MIT and Apache 2.0 are very permissive — you can use the code in almost any project. GPL requires you to share your own changes under the same terms. Creative Commons covers non-software work like 3D models and documentation.
- **"Free as in freedom", not just free of charge.** Some open source tools are free to download too, but the freedom to inspect and modify the source is the point.
- **Forks and pull requests.** Open source projects live on platforms like GitHub. You can fork (copy) a project, improve it, and propose your changes back to the original maintainers.

## How contributing works

This is the loop that makes open source improve over time. You **fork** a project (take your own copy), make it better, then open a **pull request** asking the maintainer to merge your change back into the original — so everyone benefits:

```mermaid
flowchart LR
    ORIG["Original project<br/>(e.g. SMARS)"] -->|"fork"| COPY["Your copy"]
    COPY -->|"improve<br/>(fix bug, add part)"| BETTER["Your changes"]
    BETTER -->|"pull request"| REVIEW["Maintainer reviews"]
    REVIEW -->|"merge"| ORIG
```

The same loop runs in reverse too: someone else's fix flows back into the project you rely on. That's why an open design quietly gets better while you sleep — you're benefiting from contributors you'll never meet.

## Why robot builders care

Almost every tool and framework you use as a maker is open source. That matters for three practical reasons.

First, **cost**. You can build a capable mobile robot for the price of a few cups of coffee, because the firmware, the CAD tool and the control libraries are all free to use.

Second, **speed**. Someone has almost certainly solved your problem already. There is no need to write a motor-driver library from scratch when a well-tested one is a single import away.

Third, **community**. When a design is open, other people improve it. Bugs get fixed. New sensor drivers appear. Someone adds a feature you would never have thought of. You benefit from hundreds of contributors you will never meet.

## Get started

The best way to understand open source is to actually use an open source robot project. [SMARS](/learn/smars/00_intro.html) — the Screwless Modular Assemblable Robotic System — is a great example: the 3D printable chassis and the Arduino code are both published openly, and a global community of makers has built dozens of variants on top of the original design.

If you want to go further, have a look at [HP Robots Otto](/blog/hprobotsotto.html), an open source walking robot platform with a large community behind it.

When you are ready to share your own work, put it on GitHub. The [Git element](/periodic-table/gi.html) covers the basics of version control that you will need. Giving back to the community is what keeps the whole thing running.
