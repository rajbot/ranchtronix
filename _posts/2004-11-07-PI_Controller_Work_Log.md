---
author: Dasfoo
date: '2004-11-09 10:43:51'
layout: post
title: PI_Controller_Work_Log
---

Work Log for the controller project

* 11/08/04 001:
* * Fixed annoying bug in median filter
* * Added FIR filter for setpoint
* * Cleaned up mess a bit

* 11/06/04 001:
* * Need Serial Ouput?
* * Need to add bumpless control and switching from manual to automatic mode
* * PI controller works okay, but strange pulsing and vibration when the I part is disabled.
* * Added antiwindup code so that intergrator can't wind up if the output is at max or min. 
* * Previous code just hard limited the intergrator value.
* * Designed new function [SetTestPoint,](SetTestPoint,.html) TglTestPoint, and [ClrTestPoint.](ClrTestPoint..html) 
