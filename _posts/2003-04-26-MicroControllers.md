---
author: Mang
date: '2004-12-14 21:52:57'
layout: post
title: MicroControllers
---

## [AVR](/microcontrollers/AVR.html)

8-bit RISC microcontrollers.  You get cpu, RAM, flash, eeprom, and IO on a single chip.  Down to 8 pins!  Can write in assembly, C (supported by GCC), or Basic (BASCOM-AVR).

'''Building USB devices using a PIC'''

* [some basics](http://stage.itp.tsoa.nyu.edu/~jn429/usbxtra/)
* [USB microphone project](http://www.alanmacek.com/usb/project.html)
* [IgorPlug-USB](http://www.cesko.host.sk/IgorPlugUSB/IgorPlug-USB%20(AVR)_eng.htm) - a USB implementation for the AVR - [homepage](http://www.cesko.host.sk/IgorPlugUSB/IgorPlug-USB%20(AVR)_eng.htm) [avrfreaks](http://www.avrfreaks.net/Tools/showtools.php?ToolID=459)

## PIC

* Example code in C (including PID and heater control) [here](http://www.microchipc.com/sourcecode/)
* A phase shifted PWM algorithm [here](http://www.dattalo.com/technical/theory/pwm.html) with PIC asm code [here](http://www.dattalo.com/technical/software/pic/pwm8.asm)

### I/O Expansion

One way to get increased inputs and outputs is to use external chips that do serial->parallel (for output) and parallel->serial (for input).  You use a small number of pins on the micro to talk serial to the external chips.  Some of the chips can be cascaded to get more inputs/outputs.


* Serial-input parallel-output latch: 74LS595, 74HC595
* [Mini SSC II](http://www.seetron.com/ssc.htm) - 12 channel serial servo controller for $44

----

* [Microcontroller Crystals](http://www.dvanhorn.org/Micros/All/Crystals.php)
