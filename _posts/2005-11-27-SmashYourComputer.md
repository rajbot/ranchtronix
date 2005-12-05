---
author: Mang
date: '2005-12-05 22:58:43'
layout: post
title: SmashYourComputer
---

Background/context

We have all been frustrated with our computers at some point.  We are dependent on computers in many ways, and when they fail to work properly

* we have all been frustrated
* lack of empowerment when we don't understand the internals
* * but sometimes knowing the insides is even more frustrating
* have had urge to smash the computer
* * destroy the black box
* take the computational power of computer and use it to simulate it's own destruction
* provide the opportunity for a physical expression of frustration against the unfeeling computer
* explore issues of simulated violence
* * does it make us more or less violent?
* * will you smash your computer when you get home?

Audience

* anyone who has been frustrated with their computer

User scenario

* user sees progress meter on screen
* after certain point (or pressure sensor) computer will crash
* user can press reset button to reboot
* at any point, can hit with sledgehammer
* projected image of computer breaks apart depending on force from sledgehammer

Implementation

* custom software written using OpenGL, Open Dynamics Engine for physics simulation
* AVR microcontroller code written using BASCOM-AVR
* beige computer case instrumented with sensors
* projection screen and projector
* plastic/rubber sledgehammer

Conclusion

* provides a safe environment to vent frustration
* cathartic experience
* computational power of computer can be turned against itself

References

* Survival Research Laboratories
* recurring theme, e.g. in Office Space
* burning Next cube [http://photo.simson.net/hacks/cubefire.html](http://photo.simson.net/hacks/cubefire.html)
* Perry Hoberman - Cathartic User Interface (1995) [http://www.perryhoberman.com/pages/cui/text.html](http://www.perryhoberman.com/pages/cui/text.html)

Code for reading from ADXL210 from PIC (adapted from [ITP Sensor Workshop report](http://itp.nyu.edu/physcomp/sensors/Code/ADXL202Processing)):

<pre>
DEFINE OSC 8

xTilt VAR WORD
yTilt VAR WORD
XPin VAR portc.2
YPin VAR portc.3
tx VAR portc.6
rx VAR portc.7
n9600 CON 16468
inbyte VAR BYTE
PAUSE 500

serout2 portc.6, 16468, ["Damn, this works.",10,13]

main:

	SERIN2 rx, n9600, [inbyte]
    'serout2 portc.6, 16468, ["Got this thing - ",dec inbyte, 10,13]	
	PULSIN XPin, 1, xTilt
	PULSIN YPin, 1, yTilt

    SEROUT2 tx, n9600, [DEC xTilt.HighByte, ",", DEC xTilt.LowByte]
    SEROUT2 tx, n9600, ["-", DEC yTilt.HighByte, ",", DEC yTilt.LowByte, 10,13]
	'SEROUT2 tx, n9600, [xTilt.HighByte, xTilt.LowByte, yTilt.HighByte, yTilt.LowByte]
	PAUSE 100

GOTO main
</pre>

More code.  Works!

<pre>
DEFINE OSC 8

xTilt VAR WORD
yTilt VAR WORD
xTiltMax var word
yTiltMax var WORD
xTiltMin var word
yTiltMin var word
XPin VAR portc.2
YPin VAR portc.3
tx VAR portc.6
rx VAR portc.7
n9600 CON 16468
inbyte VAR BYTE
PAUSE 500

LEDPin var portb.7  

'system test---LED blinks five times to verify code is running
i var byte
    for i = 0 to 4
        high LEDpin
        pause 200
        low LEDPin
        pause 200
        next

serout2 portc.6, 16468, ["Damn, this works.",10,13]

' Initialize to current value
initialize:
    pulsin xpin, 1, xTilt
    pulsin ypin, 1, ytilt

    xtiltMax = XTILT
    YTILTMAX = YTILT
    xTiltMin = xTiltMax
    yTiltMin = yTiltMax

main:
    PULSIN XPin, 1, xTilt
    PULSIN YPin, 1, yTilt
 
    if xTilt > xTiltMax then
        xtiltMax = xtilt
    else
        if xTilt < xTiltMin THEn
            xTiltMin = xTilt
     endif
    endif
    
    if ytilt > ytiltmax then
     ytiltmax = ytilt
    else
        if yTilt < yTiltMin THEN
         yTiltMin = yTilt
        endif
    endif
 
    'look for some serial, and if it doesn't arrive, keep sampling
    SERIN2 rx, n9600, 2, main, [inbyte]
    'serout2 portc.6, 16468, ["Got this thing - ",dec inbyte, 10,13] 

    SEROUT2 tx, n9600, ["x",hex2 xTiltMax.HighByte, hex2 xTiltMax.LowByte]
    SEROUT2 tx, n9600, [",", HEx2 xTiltMin.HighByte, HEX2 xTiltMin.LowByte, 10,13]
    SEROUT2 tx, n9600, ["y",Hex2 yTiltMax.HighByte, hex2 yTiltMax.LowByte]
    SEROUT2 tx, n9600, [",", HEx2 yTiltMin.HighByte, HEX2 yTiltMin.LowByte, 10,13]      
    'SEROUT2 tx, n9600, [xTilt.HighByte, xTilt.LowByte, yTilt.HighByte, yTilt.LowByte ]
    PAUSE 100
    goto initialize

GOTO main
</pre>
M = max, m = min

Untested.. should output as xHMLMhmlmyHMLMhmlm\10\13


<pre>
DEFINE OSC 8

xTilt VAR WORD
yTilt VAR WORD
xTiltMax var word
yTiltMax var WORD
xTiltMin var word
yTiltMin var word
XPin VAR portc.2
YPin VAR portc.3
tx VAR portc.6
rx VAR portc.7
n9600 CON 16468
inbyte VAR BYTE
PAUSE 500

LEDPin var portb.7  

'system test---LED blinks five times to verify code is running
i var byte
    for i = 0 to 4
        high LEDpin
        pause 200
        low LEDPin
        pause 200
        next

serout2 portc.6, 16468, ["Ready to smash.",10,13]

' Initialize to current value
initialize:
    pulsin xpin, 1, xTilt
    pulsin ypin, 1, ytilt

    xtiltMax = XTILT
    YTILTMAX = YTILT
    xTiltMin = xTiltMax
    yTiltMin = yTiltMax

main:
    PULSIN XPin, 1, xTilt
    PULSIN YPin, 1, yTilt
 
    if xTilt > xTiltMax then
        xtiltMax = xtilt
    else
        if xTilt < xTiltMin THEn
            xTiltMin = xTilt
     endif
    endif
    
    if ytilt > ytiltmax then
     ytiltmax = ytilt
    else
        if yTilt < yTiltMin THEN
         yTiltMin = yTilt
        endif
    endif
 
    'look for some serial, and if it doesn't arrive, keep sampling
    SERIN2 rx, n9600, 2, main, [inbyte]
    'serout2 portc.6, 16468, ["Got this thing - ",dec inbyte, 10,13] 

    SEROUT2 tx, n9600, ["x", HEX2 xTiltMax.HighByte, HEX2 xTiltMax.LowByte]
    SEROUT2 tx, n9600, [HEX2 xTiltMin.HighByte, HEX2 xTiltMin.LowByte]
    SEROUT2 tx, n9600, ["y", HEX2 yTiltMax.HighByte, HEX2 yTiltMax.LowByte]
    SEROUT2 tx, n9600, [,HEX2 yTiltMin.HighByte, HEX2 yTiltMin.LowByte, 10,13]      
    PAUSE 10
    goto initialize

GOTO main
</pre>
