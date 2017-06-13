---
layout: post
title: "GRBL Bootup"
date: 2017-06-13            
---

## Progress

Progress report from yesterday: The RAMPS 1.4 Kit arrived in the mail,
including an Arduino Mega and 5 A4899 stepper drivers.  To get it
working, I began by upgrading my Arduino IDE to 1.8.3.  Then I
downloaded the grbl-mega project and built it according to the
instructions on the wiki.  (I didn't change any of the platform
settings before building.)  Finally, I was able to download it to the
Arduino and it ran.  So now I have a G-code interpreter, I guess.

Using the serial port, I was able to issue a "$$" command to list all
the '$-parameters' of the controller.

I did not try hooking up a stepper motor yet.  I'm looking for a power
supply for it.  I had hoped to use my HALO jump starter as a 12V
source but it doesn't seem to put out any voltage on the 12V output
when it has an open circuit.  I did find a 12V 2A wall wart power
supply in the basement.  I might try hooking that up.

So next steps are:
* Set jumpers for micro-stepping.
* Set current limit potentiometer.
* Connect motor.
* Issue some G-Codes manually to start/stop motor.

After getting that far, there are further features to explore:
* Experiment with servo PWM outputs.
* Experiment with end stop inputs.
* Experiment with adjusting params in header file.

And, later, I'll want to do a proof of concept of the whole laser
cutter tool chain:
* Inkscape plugin to produce G-code.
* Tool to send G-code to GRBL.
* Confirm stepper, end stop, laser enable, laser pwm operations.




