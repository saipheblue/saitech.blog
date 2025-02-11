---
title: Funny Linux Commands
date: 2025-02-10
description: What does the cowsay?
image: 2.png
tags:
    - Arch Linux
    - Terminal
    - Tweaks

categories:
    - Linux

---
## Cowsay

Cowsay is a hilarious ASCII art tool that lets a cow (or other animals) say the text you define.

Install it using pacman:

```
sudo pacman -S cowsay
```
Use cowsay:
```
cowsay <message>
```
![cowsay hi](4.png)

For greedy eyes:
```
cowsay -g <message>
```
![cowsay -g hi](6.png)

There are other ascii animals that you can use in palce of cow you can list them using `cowsay -l` and switch them with `-f`
```
cowsay -f <animal name> <message>
```
![cowsay -f fox hi](7.png)
### Options:

* `-b` Invokes Borg mode
* `-d` Causes the cow to appear dead
* `-p` Makes the cow paranoid
* `-s` Makes the cow appear thoroughly stoned
* `-t` A tired cow
* `-y` A youthful cow
* `-r` Random animal (instead of `-f`)

### Cowthink

Want the cow to think instead of speak? Try:

![cowthink hi](5.png)

This changes the speech bubble to a thought bubble, like in comics!

## sl

The command `sl` is a fun tool created to mock the commonly misspelled `ls` command in Linux.

Install using pacman:

```
sudo pacman -S sl
```
![sl](1.png)

When you run `sl`, a train appears in your terminal. You can add more fun with various options:

* `-a`: <b>Accident mode</b> – You’ll see people crying for help. Not for the faint-hearted! ;)
* `-l`: <b>Miniature train</b> – Shows a smaller train with more coaches.
* `-F`: <b>Flying train</b> – A train like the Polar Express.
* `-e`: <b>Interruptible mode</b> – Allows interruption with Ctrl+C. In other modes, you can't stop the train. But it doesn’t last long unless you have a super-wide monitor.
* `-d`: <b>Disco Mode</b> – The train alternates colors.
* `-G`: <b>Advanced trains</b> – A new look, similar to advanced trains like the French TGV.
* `-w`: <b>Speed boost</b> – Makes the train move faster.
* `-[Number]`: <b>Custom cars</b> – Adjust the number of train cars.

![sl -G](3.png)
