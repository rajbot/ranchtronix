---
author: Dasfoo
date: '2004-11-11 04:07:51'
layout: post
title: PI_Controller_Work_Log
---

Work Log for the controller project

* 11/10/04
* * Went to Dentist, no cavities
* * Lunch with GF followed by a long nap
* * [McCabe](McCabe.html) showed me how to check in code under source forge.
* * Off to drink at the ranch
* * May try to package the blower controller

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
