---
author: Raj
date: '2005-10-03 21:44:35'
layout: post
title: HowTo_Use_A_SSH_Tunnel
---

## [HowTo](HowTo.html) Tunnel Web Traffic through SSH

Instuctions for Mac OSX:

In this example, I will use ranchtronix.org, but you can use your own
shell account. Also, I will use port 1984, but you can use whatever port
you like.

1) Open terminal and type "ssh -D1984 username@ranchtronix.org"<br>
2) Open System Preferences -> Network -> Proxies, and check the SOCKS
Proxy Server box. Add the IP 127.0.0.1:1984 as your SOCKS proxy.<br>
3) There is no step three.

Web traffic and most other network connections will now be tunneled through SSH. This is a good way to get around misbehaving filters.
