---
author: Dasfoo
date: '2004-10-06 03:36:17'
layout: post
title: Blower_Controller
---

## [AtMega8](AtMega8.html) Blower Controller

I recently found a two furnace stage blower that is powered by a brushless DC motor.   The blower speed is controlled by a PWM input.

I'm designing a control board based on an ATMega8 that will use a pressure sensor to measure the output pressure of the blower, and control it using the blowers PWM input.  (If this all sounds lame and dis-jointed well what over it.)

The controller will have the following control inputs/outputs.

Pressure Transducer
Pressure Setpoint Pot
Ecconomizer trim Pot
Ecconomizer Input SW
PWM Output
Gas Valve Output.


<b>Gas Valve Output</b>
The gas valve control is interesting.  The typing table uses a 12V valve to turn on the gas.  It might make more sense to use 120Vac valve instead.  The advantage is that the power supply would be smaller
since there is no need to run the valve off the 12V supply.

When laying out a real PCB the Gas control output should be a relay.

The controller will turn on the gas valve when the manifold pressure rises above 3 inches of water.  

<b>PWM Output</b>
The PWM output needs to be able to achieve 10V in order to operate the blowers PWM input.  The PWM input is an opto-coupler.  The is an internal filter than can convert a 150-400HZ PWM signal into a control voltage.  (Otherwise the unit expects a 0-10V analog signal.)

<b>Ecconomizer Input SW</b>
Idea here is to have an ecconomizer input so that when the ecconmizer switch is closed, the controller will reduce the manifold pressure in order to save on gas.

<b>Pressure Transducer</b>
Pressure transducter is a 0-1.5 psig silicon pressure sensor.  Output is +/- 25mV.  An insturmentation amp is used to amplify the output by 200 to 0-2.5 volts.

<b>Setpoint Pot</b>
A linear 10K pot connected between ground and VCC.  Since the A/D and pressure sensor are all ratiometric vs VCC this should work fine.

