---
author: McCabe
date: '2004-03-24 06:44:14'
layout: post
title: BatteryBooster
---

# AAA Battery Booster

This idea (and Mike's interest in voltage boosting) is due to Ted Hullar.

Ted has some LED headlamps that take 3 alkaline AAAs apiece.  A few problems with this:

* Alkaline batteries are expensive, he'd rather use NiMH, but:
* NiMH batteries have enough juice over time, but the voltage is two low to keep white LEDs happy
* Batteries are bought and charged in pairs!

I have stuff like this too.

His suggestion: A voltage booster IC and attendant passives in the shape of an AAA battery.  This replaces one of the three batteries.  The remaining two NiMH batteries add up to 2.4V, much lower than 3 alkalines' initial voltage of 4.8V.  But NiMH batteries can deliver more current, which the boost IC can turn to higher voltage.

It can fit between the positive end of the two batteries and the positive power terminal of the light.  It needs a connection to ground; this can be a discreet wire and tab wedged into ground between the battery and the negative power terminal of the light.

I prototyped it.  It worked.  It busted the same night.  I promised I'd design an IC.  Many weeks later...

Here's the pre-draft:

upload:AAA%20booster.zip 
