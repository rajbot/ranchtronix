---
author: Mang
date: '2005-11-26 04:44:34'
layout: post
title: OpenDynamicsEngine
---

Does rigid body simulation.  Used in a bunch of games.  Python version is PyODE.

I had to do this with Visual Studio 8 to compile/link:

* /NODEFAULTLIB libc.lib;msvcrtd.lib
* add lib libcmt.lib
* add include dir ode\include
* add lib dir ode\lib
* add libs ode.lib, drawstuff.lib
