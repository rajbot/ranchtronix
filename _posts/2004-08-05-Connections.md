---
author: Raj
category: AvrButterfly
date: '2004-08-05 22:47:19'
layout: post
title: Connections
---

![butterfly-ports.png]({{ site.baseurl }}/images/butterfly-ports.png)

### PortB pin connections

Connected to ISP header, Dataflash, and Joystick. Note that for joystick buttons, "The common line of all directions is GND. This means that internal pull-up must be enabled on the ATmega169 to detect the input from the joystick."

|| '''Pin''' || '''Alias''' || '''Connected to...''' ||
|| PB0 || !SS/PCINT8 (SPI Slave Select input or Pin Change Interrupt8) || Dataflash CS pin  ||
|| PB1 || SCK/PCINT9 (SPI Bus Serial Clock or Pin Change Interrupt9) || Dataflash SCK pin, ISP Header (pin 3) ||
|| PB2 || MOSI/PCINT10 (SPI Bus Master Output/Slave Input or Pin Change Interrupt10) || Dataflash SI pin, ISP Header (pin 4) ||
|| PB3 || MISO/PCINT11 (SPI Bus Master Input/Slave Output or Pin Change Interrupt11) || Dataflsah SO pin, ISP Header (pin 1) ||
|| PB4 || OC0A/PCINT12 (Output Compare and PWM Output A for Timer/Counter0 or Pin Change Interrupt12) || Joystick center (O) ||
|| PB5 || OC1A/PCINT13 (Output Compare and PWM Output A for Timer/Counter1 or Pin Change Interrupt13) || <b>dunno!!</b> ||
|| PB6 || OC1B/PCINT14 (Output Compare and PWM Output B for Timer/Counter1 or Pin Change Interrupt14) || Joystick up (A) ||
|| PB7 || OC2A/PCINT15 (Output Compare and PWM Output A for Timer/Counter2 or Pin  Change Interrupt15) || Joystick down (B) ||
