---
author: McCabe
date: '2004-03-23 08:21:52'
layout: post
title: NightLights
---

Back to [Light](Light.html).

3/22/4

Hard to believe it's been just a few months.  Lots of progress on this project.  I put the original dimmer circuit in a light for Sasha (which promptly died; I was able to fix it much later by adding a missing capacitor and praying a little.)  I did a batch of 3 with a new dimmer circuit, using PCB and surface-mount tek.  Though I improved the circuit halfway through, so the final product involved some added wires and cut traces.  I still have one; the others are with my brother and niece in Portland and with my cousin Carlos and his wife Mayling in Costa Rica: ![//latin_puck_use.jpg]({{ site.baseurl }}/images///latin_puck_use.jpg)

10/5/3

Brian Loper recommends Pearl art supplies for armature wire.  The way to go.

I spent Friday night helping Mike Estee with his surface mount low-power pic platform, future directions in pcbs and surface mount to follow.

10/1/3

Still actively hacking.. - latest is two three-light lights, each with no body but a long shrink-wrapped wire terminating in the power connector.  I'm not sure they look that good, but they can be wrapped around supporting objects.

Picking up pucks tonight.  (Went well, they guy was psyched to get the snakey blinky 3-light I made last night.  The blue bulb went out overnight, so I wasn't so reluctant to give it up.)

Should shop:
More LEDs?
More voltage regulators?
More wall wartz?

At ranchtronix: parts arrived.

    Digi-key 425-1608-5-ND --- IC REG LDO ADJ .5A ON/OFF SC-63

SC-63 seems like a dealable package - small but not too too tiny.  .5V dropout, not hot, not too bad.  $1.70, too.

HOWEVER it only has a 10V maximum; I'd prefer 14-15V to be compatible with 12V / Car systems.

What do I want from a voltage regulator / power supply?

* Small (doesn't much matter, for the pucks)
* Easy to solder (remains to be seen, with the SC-63)
* LDO - .2V would be best, but at least less than 1.5V
* On/Off - seems helpful for the light-sensor circuit
* Cheap.
* Pre-set to a useful voltage - 4? (Optional, would save lots of time)
* * 5V is common and easy to work with, but must be ultra-LDO or it'll take more than 6V to supply.  Also, it doesn't use all of an alkaline's capacity.

[http://rocky.digikey.com/WebLib/Sharp/Web%20Data/PQ070XZ(5MZ,%2001Z).pdf](http://rocky.digikey.com/WebLib/Sharp/Web%20Data/PQ070XZ(5MZ,%2001Z).pdf)

Some twisty light notes, 9/26/3.

I got the nieceproof nightlight together - 7 LEDs on poseable wire strands, in a base made out of a hockey puck I took from my brother's old stuff. 2 reds, 2 greens and 3 blues, in an attempt to approximate white. No UV leds, they're dangerous for nieces. It has a 2.1x5.5mm power jack. This one is barrel positive, though the rest will be barrel negative, as that is the variety of wall wart I got. Potted and done. Thanks to Foo for the urethane...

It needs a light sensor. I put together a circuit last night that will do the trick, along with a shutdown pin on the voltage regulator. I spent quite a while getting just the right behavior: now, when the light sensor goes dark, it turns on gradually, slowly raising the output voltage over about 20 seconds. The colors come in one by one, a gorgeous effect.

I want to make more. I need (for each) (assuming current dimmer circuit):

* Hockey puck (I have 2 currently)
* Power jack (9)
* Wall wart (4)
* Voltage regulator / power supply / booster / whatever (3 of a good kind)
* One of [these](http://www.national.com/ds/LP/LP3961.pdf) in 5-volt fixed, for the black coral?
* Photoresistor (10)
* Small MOSFET (0)
* Capacitor, 1uF (many available)
* 3906 PNP transistor (Just a few, should replace - 10 needed)
* Resistors - should check supplies
* PC board? 

Some questions:

* Power supply solution! Maybe another few one-offs to get it right...
* PC board? The dimmer circuit is now somewhat complicated. $40 + effort to try this out; the dimmer circuit is a simple way to start.
* Microprocessor control? This would obviate any dimmer circuit. And get me started in that world...
* Battery power? Integrated batteries? (Not into the hockey puck, but maybe other things...) Interested in step-up power control for this, and an integrated battery charger. (Daisy-chained charging station for 10 path lights?)
* Other chassis shapes? Hockey pucks are tight!
* What are these things called? 

Parts:

* My last mouser order:
* * 412-106054 (just 106054 to look up) 6V/500mA 2.1mm Hi-Q AC adaptors (5)
* * ME163-4303 Panel mount 2.1mm DGS DC power jacks (10) 

* Stuff from digi-key:
* * 425-1619-5-ND 9V regulators with on/off (3)
* * RC1587T-ND Adjustable regulator
* * 4251726-5-nd Adj. regulator
* * LP3964ET Adjustable Ultra-LDO regulator
* * PDV-P9007-ND photocell
* * MAX756CPA-ND DC/DC Conv Step-up 3.3/5V 8-DIP
* * MAX1675EUA-ND DC/DC Conv Step-up adj 8-uMAX
* * DN41223-ND Coil 22uH molded shielded
* * MBR1100-ND Schottky diode. 
