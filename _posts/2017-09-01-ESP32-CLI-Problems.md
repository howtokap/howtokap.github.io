---
layout: post
title: "ESP32 Updates, CLI problems"
date: 2017-09-01
---

It's been a long while since I did anything with my ESP32.  And I
still haven't performed the range test between two units that was my
original goal.

So today I started it up again.  The first thing I did was pull
updates of the esp-idf repository.

After rebuilding everything I noticed that:
  1) The download/flash process works better.  It uses compression so
  it's faster and I don't have to manually press any buttons on the
  ESP32 Thing.

  2) The CLI has messed up UART settings.  It is echoing junk.  I've
  tried all the alternative baud rates.  Changing that changes the
  junk but doesn't clear it up.

I've tried configuring for both 32K external crystal and 150K internal
oscillator but I get the same results either way.

This is frustrating.  I can't move forward until this is fixed.

(I'll have to get the logic analyzer from the office to figure out
what's going on, I guess.)

## Resolution

Using the logic analyzer I discovered that instead of 115200, the
target was using 75k baud.  That led to finding a setting in the
project configuration for the external crystal.  It was set as 40MHz
but should have been 26.  So that accounted for the discrepancy.

With that corrected, the master branch of esp-idf runs well.  And the
hack I added to separate CRLF processing for input and output isn't
necessary anymore with the updated ESP-IDF.

So the baseline software seems to be all working now.  It's ready to
make forward progress again.


