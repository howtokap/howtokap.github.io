---
layout: post
title: "Installing Android SDK"
date: 2016-12-08
---

I want to build CyanogenMod for my old Kindle Fire HD 8.9.  The Amazon
OS and software environment are ridiculously out of date.  So I'm
following instructions from here:

https://wiki.cyanogenmod.org/w/Build_for_jem

## Android SDK Installation

First step is installing the [Android SDK](https://wiki.cyanogenmod.org/w/Doc:_sdk_intro)

Downloading android-studio-ide-145.3537793-linux.zip (22 minutes)

Unzipped that into ~/opt/android-studio

Installation instructions: https://developer.android.com/studio/install.html

IDE Setup says...
    Search for install instructions for your particular Linux
    configuration (Android KVM Linux Installation) that KVM is enabled
    for faster Android emulator performance.

Installed that and created launcher icon.

Installing required libraries as suggested.

Updated .bashrc to include ~/opt/android-studio/bin

Problem: adb and fastboot executables not in path?  I expected they
would at this point.

Additionally downloading tools_r25.2.3-linux.zip to get command line tools.
Nope, adb not there, either.

Do I need to run sdkmanager to get it?  And/or other tools, too?
Need to install Platform Tools package via IDE?

Already in ~/Android/Sdk/platform-tools/
Added that to my path in .bashrc

Pick up tomorrow with installing build packages: bison, build-essential, etc.
