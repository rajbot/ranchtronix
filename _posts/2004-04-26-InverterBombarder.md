---
author: Dasfoo
date: '2004-04-26 22:55:56'
layout: post
title: InverterBombarder
---

The current Neon Bombarder uses a big ass pole pig and a magnetic amplifier to heat neon tubes and electrodes diring processing.

A major problem with this is that the high voltage high current output of the bombarder can kill.

A possible improvement would be to design an inverter type bombarder that uses a high frequency square wave to heat the tube.  The advantage could be lower voltage and a smaller foot print.  Also the thing could be designed so that if the was a problem the unit would shut down.  Might even be possible to design a GFI circuit into it.

A thought I has would be a system like this.


240VAC --> Rectifier --> Computor Controlled Inverter --> IGBT or Mosfet H bridge --> isolation transformer --> HF Start Trasnformer --> GFI Detector

The 240 VAC would enter the unit and be rectified to 480 VDC (Mommy I'm scared).

This would then be chopped by a DC to DC converter into 0-400 VDC.

Then the H bridge would feed dat into an isolation transformer to produce a 0-400 VAC square wave.

A HF start transformer would be used in seires with the square wave to impinge a HF start waveform to get the arc started.  Once the arc starts it might be self sustaining.  That is the plasma wouldn't be quenched when the power reversed.

The advantage of this is that the high frequency start could would only have to be used to start the arc.  A
current sense transformer or hall effect sensor could be used to sense the current.  If the current devitated from normal the unit could then swich off and go into fault.

Possible Faults Might Be

Open Circuit
Short Circuit
GFI Fault




