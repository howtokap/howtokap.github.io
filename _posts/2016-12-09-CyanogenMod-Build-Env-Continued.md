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

## Install ```repo``` command

```bash
curl https://storage.googleapis.com/git-repo-downloads/repo > ~/bin/repo
chmod a+x ~/bin/repo
```

~/bin should already be in path but need to start a new shell to get it.






