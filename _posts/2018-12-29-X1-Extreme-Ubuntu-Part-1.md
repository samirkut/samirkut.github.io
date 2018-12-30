---
category: Tech
tags: [X1, Ubuntu, Pop OS]
author: Samir
title: X1 Extreme on Ubuntu (Part 1)
comments: true
---

I recently acquired an X1 Extreme and spent the last day or so getting Ubuntu (to be more accurate Pop OS) to play nice with it. I have documented them below partly for my own sanity and also to ensure that any other owners can use this as a starting point.

<!--more-->

## BIOS changes

1. Turn off secure boot. 
_From what I have read it should be able to get Pop OS and secure boot to play nice but for now I am going to simply skip this._

2. Switch the Fn Key mode so that pressing F1-F12 keys does not require the Fn key pressed. 


## Installation

* Using Pop OS 18.10 amd64 nvidia edition [Pop OS](https://system76.com/pop).
* Resized windows partition to 150GB. I prefer to hang on to windows for things like BIOS patches and other testing. Plus I can always boot the windows partition from Virtualbox (this is currently untested)
* Added a 24GB swap partition. This is 1.5 times my RAM - recommended if you want to use hibernation
* Add an ext4 partition after the swap partition.
* Point the boot partition to the existing boot partition (first partition) on the disk 

## Additional Software

Added some additional software on top of Pop OS default install

### Extensions 
Installation is web based from [here](https://extensions.gnome.org). You need to install the addon (for either chrome/firefox)
* (K)StatusNotifierItem/AppIndicator Support - required to show systray icons for telegram, dropbox etc
* User Themes - manage themes
* Dash to Dock - move the dash from overview and convert it into a dock 

### Other Software
* Gnome Tweaks
* TLP - _Without this the fans keep going off every few minutes_
* Cheese - webcam/camera tester
* Chrome
* Telegram
* Dropbox - _The icon is not clickable and hence am not able to configure it_
* Other dev toole like VS Code, git, clang etc

## Display
By default Pop uses the Nvidia driver with a 200% scaling. This makes the screen really nice and crisp however I prefer more space. Unfortunately as of now there is no support for fractional scaling. So you have 2 options
1. Scale to 100% and use the gnome tweaks to change the font scaling
2. Change the screen resolution to something larger (I am using 2560x1440) and switch to 100% scaling.
Both options require you to disable the HiDpi deamon otherwise the resolution and scaling will reset after reboot

## Battery life
I am getting about 4 hours on Nvidia driver. However since I dont really play games or do any graphics, I switched to the intel driver. This increased my batter life to something more sane (around 8 hours estimated)

## External monitor
Not working so far. Need to investigate

## Fingerprint
Not working as there is no driver support [Details](https://github.com/nmikhailov/Validity90/issues/34).

## Webcam
Initially kept showing the IR image instead of the normal image. Use Cheese to change the device and things start working then

## IR login
I want to enable something like Windows Hello login. Havent tried as yet but looks hopeful [Details](https://github.com/boltgolt/howdy).

One thing to note is that this may not be as accurate as windows version since Linux is only seeing one IR device. From my understanding there are 2 IR cameras which make the detection more accurate in windows.


## Summary

Overall it didnt take as much time as I thought it would to get an end to end running Linux system. I am a bit disapoointed about the lack of finger print support and the fact that the USB-C cannot be used for external monitor but on the whole the system is fast, extremely poerful and well worth the money.