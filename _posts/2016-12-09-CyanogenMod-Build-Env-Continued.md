---
layout: post
title: "CyanogenMod Build Environment Setup (Cont.)"
date: 2016-12-09
---

## Build Packages

The next step, continuing from yesterday's start of a CyanogenMod build environment, is to install build packages.  These were the packages I used for Ubuntu 16.04:

```bash
sudo apt-get install bison build-essential curl flex git gnupg gperf \
                     libesd0-dev liblz4-tool libncurses5-dev libsdl1.2-dev \
                     libxml2 libxml2-utils lzop maven openjdk-8-jdk pngcrush \
                     schedtool squashfs-tools xsltproc zip zlib1g-dev \
                     g++-multilib gcc-multilib lib32ncurses5-dev lib32z1-dev \
                     lib32readline6-dev libwxgtk3.0-dev
```

After that, I installed the Java 7 JDK:

```bash
sudo add-apt-repository ppa:openjdk-r/ppa
sudo apt-get update
sudo apt-get install openjdk-7-jdk
```

## Create Directories

Create some necessary directories

```bash
mkdir -p ~/bin
mkdir -p ~/android/system
```

## Install repo and initialize repository

```bash
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
```

~/bin should already be in path but need to start a new shell to get it.

Now initialize Cyanogenmod Source repository

```bash
$ cd ~/android/system/
$ repo init -u https://github.com/CyanogenMod/android.git -b cm-12.1
```

Note the cm-12.1.  Instructions said cm-13 but the site says 12.1 is latest build supported on jem.

And finally...

```bash
$ repo sync
```

Started at 2:15pm...
Done by 4:30.

## Next step:

Still on this page: https://wiki.cyanogenmod.org/w/Build_for_jem

In Prepare the device-specific code section.
(envsetup and breakfast coming up.)

Ran those.  Had errors in breakfast so will take the advice in the note
from that page: Do next step to read out Blobs from device, then repeat
breakfast step.






