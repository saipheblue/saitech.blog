---
title: Gamemode
date: 2025-02-03
description: A simple command to potentially improve performance
image: 1.png
tags:
    - Arch Linux
    - Terminal
    - Tweaks
    - GameMode
    - Steam
    - Github

categories:
    - Gaming
    - Linux

---

## What is gamemode?

The command `gamemoderun %command%` is used on Linux to run a game or application with Gamemode, a tool designed to optimize your system for gaming. It tweaks settings like the CPU governor, I/O priority, and more to give your games a performance boost.

## How It Works:

`gamemoderun`: This is the command that activates Gamemode.

`%command%`: This is a placeholder for the actual command used to launch your game or app. It’s commonly used in Steam’s launch options.

Example:

If you’re running a game through Steam, you might add the following to the game’s launch options:


`gamemoderun %command%`

This ensures the game runs with Gamemode optimizations.

## Installation:

If you don’t have Gamemode installed, you can install it on Arch Linux using:


```
sudo pacman -S gamemode
```

To check if Gamemode is active, run:

```
gamemoded -s
```
This will show whether Gamemode is running.


## What Does Gamemode Optimize?

Gamemode can tweak a variety of settings to improve gaming performance, including:

* CPU Governor:
  * Locks your CPU at top speed for better performance.

* I/O Priority:
  * Gives your game priority access to your disk, reducing stuttering.

* Process Niceness:
  * Makes sure your game gets more attention from the CPU.

* Kernel Scheduler:
  * Adjusts how tasks are handled to keep your game running smoothly.

* Screensaver Inhibiting:
  * Stops your screensaver from interrupting your game.

* GPU Performance Mode:
  * Optimizes your GPU for gaming (supports NVIDIA and AMD, plus overclocking for NVIDIA).

* CPU Core Management:
  * Pins or parks CPU cores to improve performance.

* Custom Scripts:
  * Lets you add your own tweaks for even more control.

## Availability

Gamemode packages are available for Ubuntu, Debian, Solus, Arch, Gentoo, Fedora, OpenSUSE, Mageia and possibly more.

## Is It Worth It?

While not all games will see a huge improvement, Gamemode is a simple and effective way to squeeze out extra performance. If you’re a Linux gamer, it’s definitely worth a try!

For more details, check out the [Github repository](https://github.com/FeralInteractive/gamemode)


