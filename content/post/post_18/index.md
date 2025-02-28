---
title: MangoHud
date: 2025-02-28
description: Performance overlay for FPS, CPU/GPU, and more.
image: 1.png
tags:
    - MangoHud
    - Tweak
    - Tool
    - Steam
    - Launch command
    - Arch linux

categories:
    - Linux

---

Overlay for monitoring FPS, frame times, GPU usage, etc., in-game.

Install MangoHud:
```
sudo pacman -S mangohud

```
Enable MangoHud in Steam:

Go to Game Properties → Launch Options and add:
```
MANGOHUD=1 %command%
```
Limit FPS to 60:
```
MANGOHUD_CONFIG=fps_limit=60 %command%
```

![](1.jpg)
