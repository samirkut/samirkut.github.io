---
category: Tech
tags: [X1, Ubuntu, Pop OS]
author: Samir
title: X1 Extreme on Ubuntu (Part 1)
---

I recently acquired an X1 Extreme and spent the last day or so getting Ubuntu (to be more accurate Pop OS) to play nice with it. I have documented them below partly for my own sanity and also to ensure that any other owners can use this as a starting point.

<!--more-->

## BIOS changes

1. Turn off secure boot. 
_From what I have read it should be able to get Pop OS and secure boot to play nice but for now I am going to simply skip this._

2. Switch the Fn Key mode so that pressing F1-F12 keys does not require the Fn key pressed. 


## Installation

- Using Pop OS 18.10 amd64 nvidia edition. Refer to [Pop OS](https://system76.com/pop)
- Resized windows partition to 150GB. I prefer to hang on to windows fo rthings like BIOS patches and other testing. Plus I can always boot the windows partition from Virtualbox (this is currently untested)
- Since I someday hope to use hibernation added a 24GB swap partition (which is 1.5 times my RAM)
- The remaining space was given over to linux
- Point to the boot partition to the existing first partition on the disk 

The installation was generally smooth with minimum hiccups.


## Summary


- [x] HiDpi display and switching between intel and nvidia drivers (although it seems to require a reboot to take effect)
- [ ] External monitor using intel drivers (from what I can figure out this should work with Nvidia)
- [x] Wireless (out of the box which is a first for me)
- [x] Sound
- [ ] Fingerprint reader (seems there is no driver support). [Details](https://github.com/nmikhailov/Validity90/issues/34)
- [x] Webcam works but needs some changes
- [ ] IR camera still to be tested but looks hopeful. [Details](https://github.com/boltgolt/howdy)
