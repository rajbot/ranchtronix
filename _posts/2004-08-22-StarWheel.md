---
author: Raj
date: '2004-09-27 22:13:25'
layout: post
title: StarWheel
---

[http://orbelisk.com/wheel/sw2.jpg](http://orbelisk.com/wheel/sw2.jpg)

mang's tasks:

* <s>dmx low level sending code</s> (thanks MikeS!)
* <s>software uart (only need receive)</s>
* <s>create protocol for sending TX->RX</s>
* * transmitter UI -> 9600 serial -> DMX output
* * prolly similar to midi
* * need to handle dropped bytes
* ** send multiple times? only accept complete packets?
* code to read adc + hw (knobs, sliders)
* <s>code to read rotary encoder (big spinny thing)</s>
* pwm code for status LEDs (if time)
* <s>cut faceplate for TX</s>
* * drill holes for switches, etc
* mount receivers in project boxes
* * mount battery holders to boxes
* set up first RX as repeater?

RF TX:

    * AVR (mega8)
    * ISP header
    * TX module
    * antenna
    * 16MHz xtal + caps
    * knobs
    * sliders
    * battery pack
    * big spinny thing (hue wants to wrap and spin) 

RF RX:

    * AVR (mega8 or mega16)
    * ISP header
    * RX module
    * antenna
    * 16MHz xtal + caps
    * DMX hardware
    * battery pack 


    >> Here's what I was thinking for the controller:
    >> 
    >> - 5 buttons to select different patterns
    >> - 1 slider each for R, G, B (or maybe just think param 1,2,3)
    >> - a speed knob (maps to -127 to 127)
    >> - a strobe speed slider with on/off toggle at the top


    Right now the fixture has the following DMX registers:
    0 - Strobe speed, 0==off (strobe toggles between max and current Value)
    1 - Hue cycling speed, 0==off, use HUE register.
    2 - Hue Hi byte
    3 - Hue low byte
    4 - Saturation 
    5 - Value

    We'll want to add:
    6 - Mode/Pattern


![starwheel.jpg]({{ site.baseurl }}/images/starwheel.jpg)
