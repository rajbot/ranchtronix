---
author: Mccabe
date: '2004-09-13 19:21:27'
layout: post
title: Powering_LED_Widgets
---

Back to [Light](Light.html).

# Ongoing thoughts and experiments on powering LEDs

They're slightly tricky to power, especially as I want full brightness all the time from batteries and wall power...

I've been using the ballast resistor method -

[http://www.bit-tech.net/article/68/](http://www.bit-tech.net/article/68/)

## Batteries [#Batteries]

Batteries by themselves are a little hard to work with, especially alkalines.  They produce 1.6 volts to start, but the voltage decreases throughout their working lifetimes.  Simply putting a resistor in series with the LED - working with 1.6 volts to not overdrive the LED - means that the light will only be brightest with absolutely fresh batteries. <b>Totally intolerable.</b>

## Wall warts

I've been using 6V/500mA (2.1mm/5.5mm dc connector) adapters from Mouser.  They're pretty small and inoffensive as wall warts go.  Part #106054.  They're not regulated, so they still require some kind of current/voltage regulation.  I did my first design barrel-positive, but the rest of the world (and the warts I got) are barrel-negative, so that's how it will be.

Mouser has nice power jacks: ME163-4303.

A page on wall warts: [http://www.powerstream.com/Wall-mount-FAQ.htm](http://www.powerstream.com/Wall-mount-FAQ.htm)

## [Voltage regulators](http://www.national.com/appinfo/power/files/f4.pdf)

My current approach.  I've been slapping low-drop-out linear voltage regulators in front of the LEDs, and adding ballast resistors from there.  Unfortunately, low-drop-out regulators *aren't*.  The cheap ones drop more than a volt - no good when using batteries.  They let me run on 6v and 12v both, though.

I'm trying 'ultra LDO' regulators - [LP3964ET](http://www.national.com/ds/LP/LP3961.pdf) from digi-key.  Not quite as LDO as I'd like (how much?) but the shutdown pin works good...  One serious problem - it only goes up to 7.5 volts Vin.  Another regulator before it?

    *Question* - if an LDO is below-voltage, does it still drop out?
    *Another* - How about reverse current protection?  Rectifier?

## Current regulators

Voltage regulators can be configured as current regulators... small-package LDOs instead of ballast-resistors, for LED chains?

Also [MAX1916](http://www.maxim-ic.com/quick_view2.cfm?qv_pk=3025) - 3 current-regulators in one package.  Maybe also facilitates pwm-less dimming?

## Step-up DC-DC converters

A [MAX756CPA](http://rocky.digikey.com/WebLib/Maxim/Web%20Data/MAX756,MAX757.pdf) is running a little green light in the foyer.  Another good option, needs a regulator though.  This worked well for the [BatteryBooster.](BatteryBooster..html)

## Step-up/Step-down converters

If we're running off of battery or wall voltage above that of the LED voltage, will need some kind of step-down - or an additional linear voltage regulator.

- [Mike [McCabe](Mike_McCabe.html)](McCabe](Mike_McCabe.html).html)
