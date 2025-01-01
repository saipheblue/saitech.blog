---
title: Quest 3 on Arch
date: 2024-12-30
description: Guide to setting up wireless SteamVR on Arch Linux
image: 3.jpg
tags:
    - Steam
    - VR
    - Arch Linux
    - ALVR
    - SideQuest
    - Quest 3
    - Oculus
    - Meta
    - SteamVR
categories:
    - Linux
---


There are plenty of guides online on how to set everything up on Windows, but not so many for Arch Linux or Linux in general.


# SteamVR
SteamVR is the backbone of PC VR gaming, supporting a wide range of headsets and offering access to countless VR titles.
It is part of your Steam library—just download and run it.

If you've previously used your headset on Windows, you might encounter an issue with Steam Link on Linux. It displays the error:

`'Streaming VR is not available from that computer.'`

Due to this limitation, we need to use alternative software to pair with SteamVR.

![](1.png)

# SideQuest

SideQuest is a popular platform for sideloading apps, games, and experimental software onto standalone VR headsets. It expands the possibilities of your VR device beyond the default app store.

Visit the official [SideQuest site](https://sidequestvr.com/) for a detailed guide on how to connect your headset, enable developer mode, and install all prerequisites.

If you're having trouble connecting your headset, ensure you have ADB (Android Debug Bridge) installed. To check, run:

```
adb version
```

If it’s not installed, you can get it with:

```
sudo pacman -S android-tools
```

# ALVR (Air Light VR)

![](2.png)

ALVR allows wireless PC VR gaming by streaming games from your PC to a standalone headset like the Meta Quest series. It uses low-latency video encoding to provide a seamless experience.

Download ALVR from the official [ALVR GitHub releases page](https://github.com/alvr-org/ALVR/releases)

* Install the APK on your headset using SideQuest.
* Extract the `.tar` file on your Arch Linux machine and run the executable.

![](4.png)

Follow the on-screen instructions to set up ALVR. Be sure to mark the headset as "trusted."

Once done, start SteamVR.

From there, <b>manually start</b> VR games from your PC. While this is a limitation, once the game is running, you can enjoy your session in the VR headset.

# Fix for Black Screen on Headset

If your VR game runs on your PC but your headset displays a black screen, try this fix:
Add the following command to SteamVR's launch options:

`~/.local/share/Steam/steamapps/common/SteamVR/bin/vrmonitor.sh %command%`

<i>(Note: File paths may vary depending on where you installed SteamVR.)</i>

# Happy gaming ! :)
