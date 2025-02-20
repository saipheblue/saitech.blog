---
title: Arch News Alert
date: 2025-02-20
description:  A simple Polybar notification system to track Arch Linux news, especially manual interventions.
image: 3.png
tags:
    - Arch Linux
    - Bspwm
    - Polybar
    - Tiling Windows Manager
    - Tweaks

categories:
    - Guide
    - Linux


---
## Why?

I got tired of manually checking [archlinux.org/news](https://archlinux.org/news) every day just to see if there were any critical updates requiring manual steps (you know, the dreaded `manual intervention`). So, I decided to automate it by adding a simple notification to my Polybar that shows the latest news headline.

When clicked, the notification disappears, and if manual intervention is required, it highlights the alert with exclamation marks—ensuring important updates aren’t missed and the system stays stable.

![](2.png)

## Module

Add the following to your module file inside your rice folder:

```
[module/arch_news]
type = custom/script
exec = /home/saiphe/.config/bspwm/src/arch_news.sh
interval = 10  ; fetch every 10 seconds, adjust as needed
format-prefix = ""
format-underline = #5E81AC

click-left = /home/saiphe/.config/bspwm/src/arch_news.sh clear && xdg-open https://archlinux.org/news/
```

## Config

Now, include the new module in your Polybar configuration. Add `arch_news` to your module list, along with a separator `sep` if you prefer.

Example:

```
modules-center = arch_news
```

## Script

Save the following script as `arch_news.sh` in your `bspwm` script directory `~/.config/bspwm/src/`

```
#!/bin/bash

# File to store the last displayed news
NEWS_FILE="$HOME/.cache/arch_news_last"
STATE_FILE="$HOME/.cache/arch_news_read"  # New file to track read state

# URL for Arch Linux News RSS feed
FEED_URL="https://archlinux.org/feeds/news/"

# Function to fetch the latest news
fetch_news() {
    curl -s "$FEED_URL" | grep -oP '(?<=<title>).*?(?=</title>)' | sed '1d' | head -n 1
}

# If called with "clear", mark as read
if [ "$1" == "clear" ]; then
    echo "" > "$NEWS_FILE"
    touch "$STATE_FILE"  # Mark the news as read by creating the file
    polybar-msg action "#arch_news.hook.0"  # Trigger Polybar refresh after clearing news
    exit 0
fi

# If we have marked the news as read, hide it on polybar
if [ -f "$STATE_FILE" ]; then
    echo "" # To make it disappear leave empty or add "✅ Up-to-date"
    exit 0
fi

# Fetch or read cached news
if [ ! -f "$NEWS_FILE" ] || [ -z "$(cat "$NEWS_FILE")" ]; then
    news=$(fetch_news)
    echo "$news" > "$NEWS_FILE"

else
    news=$(cat "$NEWS_FILE")
fi

# If no news, show nothing
if [ -z "$news" ]; then
    exit 0
fi

# Highlight if manual intervention is needed
if echo "$news" | grep -iq "manual"; then
    echo "⚠️ --- $news --- ⚠️"
else
    echo "📰 $news"
fi

```

Make the script executable:

```
chmod +x ~/.config/bspwm/src/arch_news.sh
```

## Usage

Simply wait for new news to be released. Clicking the notification will open the news in a new browser tab. After 10 seconds, the alert will disappear from your Polybar until fresh news is available. If manual intervention is required, exclamation mark symbols will be added to grab your attention.
