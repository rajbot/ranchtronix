---
author: Dasfoo
date: '2004-08-01 07:51:30'
layout: post
title: Brushless_DC_Motors
---

Blushless DC Motors are cool, they are quiet and reliable like AC motors, but have the electrical specs of DC motors (speed and torque are proportional to applied voltage)

The downside is that control circuit is much more complicated.  Where DC motors have a
commutator that switches the coil voltages, a brushless dc motor has no commutator and the voltages need to be switch externally.  Which means you need a way of measuring the rotor position.  Two ways to do this, with a hall effect sensor, or sensorless by using the back emf of one of the coil windings.

An App note that explains how to do this using a PIC 

[http://ww1.microchip.com/downloads/en/AppNotes/00857a.pdf](http://ww1.microchip.com/downloads/en/AppNotes/00857a.pdf)

The motor that used was a Pittman N2311A001



