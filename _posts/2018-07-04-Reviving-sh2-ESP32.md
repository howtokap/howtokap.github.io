---
layout: post
title: "Reviving SH2 ESP32 project"
date: 2018-7-3
---

Today I did some work on reviving my sh2_esp32 project.

Steps taken:
* Installed xtensa toolchain on new Ubuntu system (aw17-r4)
* Made a new clone of sh2_esp32
* Verified that BNO080 I2C interface still works.  (Based on original bno080 demo code.)
* Cleaned up warnings.
  * Changed esp_task_wdt_feed() calls to _add() and _reset().
  * changed "task" to "port" on critical section calls
  * added scan_type, scan_time components to scan param struct.
* Suppressed prints from sensor app. (To allow CLI to work.)
* Configured minicom to permit CLI operations.
  * Set line
  * Set comm params
  * Disable hardware handshaking (key!)
  * Save as default once working.
* Added quoted param support to CLI

At this point, I can run it, scan for APs, connect to a know AP with
the STA command.  The system connects, gets an IP and reflects the
changing state on the LED.

_
