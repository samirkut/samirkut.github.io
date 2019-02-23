---
layout: posts
category: Tech
tags: [X1, Ubuntu, VPN, OpenVPN]
author: Samir
title: OpenVPN on Ubuntu 18.10
comments: true
---

I thought configuring OpenVPN on ubuntu would be automatic but turns out there are some things that you need ot watch out for.

<!--more-->

I recently setup an OpenVPN server and decided to configure my laptop (running Pop OS/Ubuntu 18.10). It seems that while  PPTP is supported out of the box, for openvpn a couple of packages need to be installed.

```
sudo apt install network-manager-openvpn-gnome
sudo service network-manager restart
```

This enabled the OpenVPN client.ovpn file to be imported using the network manager. However I was still getting an error 

```
Invalid VPN service type (cannot find authentication binary)
```

Quick googling led to this [site](https://necromuralist.github.io/posts/openvpn-on-ubuntu-1804/). So edit the  /etc/NetworkManager/system-connections/... file as advised.   

_One deviation is that I did not need to put quotes around the password. In fact adding quotes gave authentication failures instead._



