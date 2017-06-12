---
layout: post
title: "Maker Summer"
date: 2017-06-12
---

It is time, once again, to revive the howtokap blog.

Since Ian and Casey have decided not to join swim team, I expect to
have a lot of free time on my hands in June and July.  So I'm looking
forward to a lot of KAP and general Maker activities.

Things are already starting to move in several directions at once so I
wanted to get some things down in a blog post.

## Dynamic Spreader

As part of WWKW 2017, I decided to make a dynamic spreader for my LDL
kite.  That was completed during the weekend of 6/3, 6/4.  Most of the
effort was in hand drilling, cutting and sanding these little plywood
sliders.  Working on it made me wish I had a laser cutter.

By the end of the weekend, the new DS was working fine.  But that
laser cutter idea was starting to grow.

## DIY Laser Cutter?

A little research online revealed that an entry-level laser cutter
from a reputable company costs about $8000.  That's a non-starter for
me.  I can send jobs to Ponoko, of course, but that takes a couple
weeks to turn around and is fairly expensive.  (~$25 for a small sheet
of plywood parts.)

But another option is to buy a Chinese "K40" laser cutter via Amazon.
These have a reputation for being almost ususable as shipped but
there's sufficient documentation online to convert it for use with
Open Source control components.

(link to DIY laser cutter blogs)

This got me to researching RAMPS 1.4, Arduino CNC shields, GRBL,
Inkscape G-code plugins, etc.

The basic workflow seems to be something like this:
* Design starts as an SVG file in Inkscape.
* Inkscape plugins convert to G-code machine paths.
* G-Code is transmitted to Arduino (Mega) running GRBL.
* Arduino controls steppers, laser on/off, laser power via RAMPS 1.4
board.
* K40 laser cutter provides the laser and mechanical components: x-y
movement, housing, etc.

Most blogs describe additional modifications to improve ventilation,
add end stops, etc.

## GRBL for other CNC applications?

Reading up on GRBL and RAMPS made me realize it's suited for many
types of CNC.  RAMPS was originally for 3D printers.  It also can be
used in CNC routers.  I'm wondering if I could use it for a telescope
mount.

So I decided to buy an Arduino/RAMPS 1.4 kit with A4899 stepper
drivers.  The package was only $40 and it should enable me to
experiment with all the capabilities of RAMPS, GRBL and a variety of G-Code
producers and senders.

That package should arrive today.

## Kite Builds

Another KAP-related project that I'm in the planning phase for: Two
new kites, an R8 Dan Leigh Delta and an R11.

I've been studying Dan Leigh's site, comparing his delta design notes
with actual photos and measurements of R-series kites.  I think I've
figured out how the general plan applies to these specific models.

(One ambiguity: is the nose angle 90 or 94 degrees.  Measurements of
some instances imply 90 but Dan Leigh's notes imply 94.)

So kite sewing is in the plans for June.

## More stuff

Other projects in various states of progress:
* New ESP32-based KAP transmitter and receiver.
* BNO080 module
* Light stick for light painting at the beach.
* Start learning SDR, Cubesat receiver antenna.
* Deep learning and Image processing.
* SLAM for robotics.
* Submarine project.
* Solar eclipse prep.

## Wrap Up

I realize I can't actually tackle all of that but it should be a fun
summer working on any of it!

