---
author: Sazz
date: '2004-09-11 17:48:35'
layout: post
title: MiniDisco
---

[http://bostoncoop.net/~mike/fossil/minidisco.jpg](http://bostoncoop.net/~mike/fossil/minidisco.jpg)

The Mini disco is a back-packable mechanical disco ball, with lights, contained within a snow globe and uses a 4 "C" battery pack power source.

* Version 1 of the mini disco has LED track lighting, using 2 brass wires and resisters soldered at each LED site.  Voltage divider wireing was used for the motor, along with a 100 ohm pot, to allow change in speed of the disco ball from "Gabber" to "Barry White." 

* Version 2 the motor is now controlled with a 1K pot hooked up to a circuit board with a voltage regulator and diode.  The LED's are wired for connection to an AVR Ass Butterfly for throbby capability
[http://bostoncoop.net/~mike/fossil/poweryourdisko.jpg](http://bostoncoop.net/~mike/fossil/poweryourdisko.jpg) 

* *Problems with the AVR heating and not all of the lights lighting up.  Raj suggests: "Yup, sound like your LEDs were connected directly to the micro! Gerneral practice is to use something like the ULN2003 darlington drivers, cause the AVR can't source that much juice!"

* *Using the Darlinton worked!  Calculating a votage drop of 1 for the driver, I placed them in a circuit with approprite resitors for each LED.  The circuit allowed us to connect the LED's to the AVR without blue smoke! Mike improved the butterfly's programming to automatically start up in throby mode each time the mini disco was turned on. The effect is very good!

* 9/8 The mini disco was filmed by a group making a documentary "In Search of the Valley" I wonder if it'll make the cut!
