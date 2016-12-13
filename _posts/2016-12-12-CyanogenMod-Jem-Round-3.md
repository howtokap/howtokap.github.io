---
layout: post
title: "CyanogenMod for Kindle Fire, Round 3"
date: 2016-12-12
---

Resuming build of CyanogenMod for Jem.

## Extracting proprietary blobs

Connected my device and did this:

```bash
$ cd ~/android/system/device/amazon/jem
$ chmod a+x extract-files.sh
$ extract-files.sh
```

That just got me a stream of errors.  adb can't connect to the device.

The instructions note that the device needs to be ALREADY running the
CyanogenMod build in order for extract-files to work.  Seems like a
bit of a chicken/egg problem!  But I guess I can install a prebuilt
image to get past this step.

Having difficulty getting Kindle into fastboot mode with the Linux VM so trying to do this on Windows directly.  There, I was able to get into fastboot mode by running the fastboot command:

```bash
$ fastboot -i 0x1949 getvar product
```

Then shut down the device, plugged it in to the USB port of the PC and
up it came into fastboot.

Downloading cm-12.1-20161016-NIGHTLY-jem.zip and associated recovery.img

Also downloading Open GApps ARM/5.1/nano from opengapps.org.

Installed those according to instructions.  And it works!

CyanogenMod is now running on the Kindle Fire.

Installing Chrome at last.  Ahh.........

## Back to the Blobs

With CyanogenMod actually running now, I extracted the blobs per the
instructions.  A couple issues I ran into: some of the .sh files were
not executable in the devices/amazon/jem directory and one of it's
siblings it was calling over to.  And one file wasn't found on the
device, bcm2076_26mhz.hcd.  I take it that's an LTE file and this
isn't an LTE device, though.

So with the blobs extracted, I repeated the breakfast jem step.  No errors this time.

I set up USE_CCACHE and set the cache size to 50GB per instructions.

Finally I started the build:

```bash
$ croot
$ brunch jem
```

And the build failed.

```bash
*** No rule to make target 'vendor/amazon/jem/proprietary/vendor/firmware/bcm2076_26mhz.hcd'
```

So maybe that firmware file was needed after all.

Found tips on how to get it here:

http://forum.xda-developers.com/kindle-fire-hd/8-9-inch-help/kindle-fire-hd-8-9-bluetooth-rom-t3315904

Not sure that's quite what I need, though.

I found that on the device, there's a file, /system/vendor/firmware/bcm2076_20mhz.hcd.  Is that the file that's actually needed?  The extract-files script did extract the 20mhz version.

Maybe copying the 20mhz firmware to a file with the 26mhz name would
be harmless?  I mean, this device doesn't seem to need the 26mhz
firmware so if it were actually loaded, I think the 20mhz file would
be best!

Re-running brunch to find the file that caused the error again.
Brunch is doing a bunch of compiles?  I thought it would immediately
hit this error again.  Nope, brunch is building for much longer and
not halting.

After 1:18:09, it failed again because of the missing firmware:

```bash
target arm C: zip <= external/zip/src/unix/unix.c
make: *** No rule to make target 'vendor/amazon/jem/proprietary/vendor/firmware/bcm2076_26mhz.hcd', needed by '/home/dwheeler/android/system/out/target/product/jem/system/vendor/firmware/bcm2076_26mhz.hcd'.  Stop.
make: *** Waiting for unfinished jobs....
```


