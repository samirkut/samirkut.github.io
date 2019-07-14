---
layout: posts
category: Tech
tags: [X1, Ubuntu, i3]
author: Samir
title: i3wm on Ubuntu 19.04
comments: true
---

Some notes on the configurations for i3wm to make it play nice with Ubuntu.

<!--more-->

# Packages installed:
 - i3wm
 - i3lock
 - i3bar
 - mc
 - links
 - xbacklight
 - pulseaudio-utils
 

# Config changes below

```

# Telegram
exec --no-startup-id telegram-desktop

# Dropbox
exec --no-startup-id dropbox start

# Launch gnome settings
exec --no-startup-id /usr/lib/gnome-settings-daemon/gsd-xsettings

# i3lock
bindsym $mod+Shift+x exec i3lock -d -c 000000

# Pulse Audio controls
bindsym XF86AudioRaiseVolume exec --no-startup-id pactl set-sink-volume 0 +5% #increase sound volume
bindsym XF86AudioLowerVolume exec --no-startup-id pactl set-sink-volume 0 -5% #decrease sound volume
bindsym XF86AudioMute exec --no-startup-id pactl set-sink-mute 0 toggle # mute sound

# Sreen brightness controls
bindsym XF86MonBrightnessUp exec xbacklight -inc 20 # increase screen brightness
bindsym XF86MonBrightnessDown exec xbacklight -dec 20 # decrease screen brightness

```

# Issues: No touchpad

Added the following file /usr/share/X11/xorg.conf.d/90-touchpad.conf

```
Section "InputClass"
        Identifier "touchpad"
        MatchIsTouchpad "on"
        Driver "libinput"
        Option "Tapping" "on"
                Option "TappingButtonMap" "lrm"
        Option "NaturalScrolling" "on"
        Option "ScrollMethod" "twofinger"
EndSection
```

# Issue: Volume key doesnt work

Added the file /usr/share/X11/xorg.conf.d/91-backlight.conf

```
Section "Device"
    Identifier      "Device0"
    Driver          "intel"
    Option          "Backlight"      "intel_backlight"
EndSection
```

# Issue: Bluetooth status

No way to see status on the bar. Juse use bluetoothctl to pair/unpair/see devices/connect/disconnect etc. Works decently well.
