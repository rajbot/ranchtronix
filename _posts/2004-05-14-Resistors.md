---
author: Raj
date: '2004-05-14 23:20:16'
layout: post
title: Resistors
---

Mr. Foo on pullup resistors:

<pre>
> I am trying to determine when I need a pullup resistor.
[snip]

* poink*


I'll tell you straight and now.

The base deal is that standard CMOS inputs are very high impedance.
That is they don't source nor sink current.  Think of them as a
small capacitor of around 10 pF.

The problem you can have is that stray currents can cause the voltage
on a 'floating' pin to be anywhere between 0 and whatever the supply
voltage is.  This is bad.

In practice you just need to make sure that the pin is always driven
by _something_ whether it's another logic gate, pullups, etc.  Just
remember that a 'floating' (unconnected) pins state is undefined
and thatz bad practice. (meaning it might not bite you in the butt,
but it very well could and cause you to pull out your hair)

The flipside of all this is that many microcontrollers now have
internal pullups so you don't need to add external ones.

Me, I usually configure unused pins as outputs and call it a day.

PS: If you're designing a switch matrix, then you need pullups.
    Either external or internal.  Check the port info on the data
    sheet.

PSS: Standard pullups for CMOS is 47k ohms.

Mr Foo
</pre>
