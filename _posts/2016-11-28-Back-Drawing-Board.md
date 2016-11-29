---
layout: post
title: "Back to the Drawing Board"
date: 2016-11-28
---

I've started working on a fresh approach to using OpenSCAD.
Previously, I wrote OpenSCAD code directly.  Now I'm trying to use
SolidPython to generate the code.

![Spar](/image/20161128/spar.bmp)

SolidPython uses Python classes to represent OpenSCAD operations.

I'm going a bit further and defining my own class hierarchy to
represents different types of parts and assemblies.  The root class is
Part, and it has methods for reading out a model, a layout or a BOM.
I'm hoping I can build up a full KAP rig design in this framework,
then easily produce the laser cutting file and a bill of materials.




