---
layout: post
title: "Thoughts on CNC KAP Rig"
date: 2018-3-22
---

Yesterday was a snow day and I spent some time learning more about
Solidworks and the Shapeoko.

I'm trying to decide if I should jump in and purchase a Shapeoko.  I
figured before spending the money I could try out the workflow to see
if I would really be able to do what I want with it.  So I drew up
part of a KAP rig, based on aluminum angle stock, exported the shapes
as dxf files from solidworks, imported those into Carbide Create, set
up tool paths, exported the G-code and simulated the milling operation
in Camotics.

The CAD portion of this I did earlier in the week.  And the CAM steps
I completed yesterday morning.  There were a few hiccups along the
way.  For instance, importing the DXF into Carbide Create it
interpreted mm as inches so I had to set a scaling factor.  But
nothing was fundamentally broken and I was able to work through it all
in half a day.

So I think I'm at the point where I need an actual Shapeoko machine to
take this to the next step -- cutting aluminum.

![SolidWorks Model](image/20180322/SolidWorks1.png)

![Carbide Create Job Setup](image/20180322/Carbide Create 1.png)

![Carbide Create Toolpath](image/20180322/Carbide Create 2.png)

![Camotics Simulation](image/20180322/camotics1.png)



