---
author: Raj
date: '2004-08-02 07:19:40'
layout: post
title: AmbienceAmbulance
---

![ambamb.jpg]({{ site.baseurl }}/images/ambamb.jpg)
<br><small>picture taken from the [AmbAmb](AmbAmb.html) Tribe</small>

[Ambience Ambulance home page](http://www.ambienceambulance.org/)

### the big ass sign

* mount rectangles on thin plywood
* spray paint plywood orange
* "Ambience Ambulance" and Man on thin plexiglas
* plexiglas on spacers 1-2" off plywood

### electrical system

* have control panel with "drive" and "parked" modes
* when parked, power 12V off power supply hooked to genny

### EL sequencers

* build own EL-sequencer
* AVR micro
* SMT EL inverters
* solid-state relays or maybe just transistors
* 12V input
* RS-232 for programming
* sealed box with DB9 connector for EL
* * 8 channels + common ground
* get boards made

### 2003 Amb Camp
from bob:

<pre>
i now know what our location out on the playa will be! we will be camped
on 6:30 either at gospel or reality (the 6th or 7th street down). it all
depends on where we find good space for our camp. in the nomenclature of
the streets this year, that means that we'll be at either "sublime gospel"
or "sublime reality" or somewhere very near there. camp conexus, for those
who are interested, will be at 6:30 and dogma. the black rock city map is
available here:
[http://www.giantmonster.com/burn2003/](http://www.giantmonster.com/burn2003/)
</pre>


### Light Bar Patterns
<pre>
#################
# Light bar pattern
10000000 300 
01000000 300
00100000 300
00010000 300
00001000 300
00000100 300
00000010 300
00000001 300
00000010 300
00000100 300
00001000 300
00010000 300
00100000 300
01000000 300
# Repeat
# End of line
#############################

############################
# Light Bar Sequence 2
10000001 300
01000010 300
00100100 300
00011000 300
00011000 300
00100100 300
01000010 300
# Repeat
# End of line
#############################

</pre>
