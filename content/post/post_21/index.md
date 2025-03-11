  ---
title: Xbox Controller on Linux
date: 2025-03-10
publishdate: 2025-03-10
description: Not Working? Yeah, Figures.
image: 1.png
tags:
    - Steam
    - Application
    - Arch Linux
    - Tweaks
    - Xbox
    - Controller
    - Configuration

categories:
    - Linux

---

Alright, straight to it—I spent way too much time fighting with my Xbox controller on Linux. It said it was connected via Bluetooth, but nope, constant disconnects like a flakey Wi-Fi signal.

Turns out, the fix was simpler than expected. Huge thanks to <b>[this](https://plug-world.com/posts/fixing-xbox-bluetooth-controllers-in-arch-linux/)</b> blog post for pointing me in the right direction.



First, make sure you have the kernel headers:


```
sudo pacman -S linux-headers
```
Then, install xpadneo, which fixes a bunch of Xbox controller nonsense:

```
yay -S xpadneo-dkms-git
```

Here’s the kicker—you have to update your controller’s firmware, and Microsoft, being Microsoft, only lets you do it on Windows.

So either:

*  Boot into Windows (if you have it)
*  Use a Windows VM

Reboot, reconnect, and boom—your controller should finally work without dropping every five seconds.

Hope this saves someone the headache I had. Happy gaming! 🎮
