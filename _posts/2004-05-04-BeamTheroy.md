---
author: Dasfoo
date: '2004-05-04 18:18:18'
layout: post
title: BeamTheroy
---

!

The bending of beams if very complicated.  Now days real mechanical engineers use computers and software to do all the hard work.  Whatever!
----
<b>Section modulus</b>

So the most important issue related to how much load a beam can take is the section modulus.  So here is the dirty secret!  When a beam bends is bends along an axis called the nuetral axis.  Material along the nuetral axis doesn't stretch.  No stretching, no force, no resistance to bending.  Stuff on the outside of the beam stretches lots, lots of stretching, lots of force resisting the bending.

The better a beam is at resisting bending the stiffer it is.  The section mondulus simply tells us how stiff a beam is.  The root equation used to find the section modulus is this:

dI = y^2 dA;  

Where dI is a bit of section mudulus
y is the distance from the nuetral axis
dA is a bit of area in the beam

Basically dI is the contribution that dA makes to the beams stiffness.  If you add up all the contributions of all the little areas you get I.  Mathamaticians call this integrating.  Fuck them! It's addtions and they know it.

What is interesting here is day y squared term y^2.  What it means is that if a bit of area is twice as far away from the nuetral axis it contributes four times as much to the stiffness.  Whta this means is that if we double the size of the beams cross section we increase the stiffness by 16 times.  This is because the area increases 4 times and the contribution of that area because of the y^2 term increases 4 times.  And 4 times 4 is 16!

This is really important cause it means that by putting material on the outside of a beam as far away from the nuetral axis as possible, we can make the beam many times stiffer.  This is important because in this case all things being equal, stiffness equals strength.

This is why tubing is so much stiffer than an equal weight rod.  All the material is placed on the outside where it can do some dammed good.

----
<b>Moment</b>

What the fuck is this?  Moment is what engineers call bending forces.  Instead of something being strected or compressed, the thing is bent.  The amount of bending force is the moment.  The moment is simply force acting against a lever arm.  

This if I have Scott weighing in at 200 lbs hanging off a 4 foot bar, I have a moment of 800 ft-lbs. On the other hand if I have Kiki weighing in at 100 lbs hanging off an 8 foot bar, you still have 800 ft-lbs.

So if Kiki and Scott are hanging off two ends of a balanced 12ft bar, how stiff does it have to be to hold there weight?  We can't asnswer without knowing how strong the material is and how stiff it is.
----
<b>Stress!</b>

What the fuck is dat!

Stress is easy.  It's just the force applied per unit area.  It's also in psi like young mudulus.  But unlike youngs mudulus the psi actually measn what you might thing it means.

Why is stress important.  Cause things break when the stress gets too high.  Steel will fail if the stress goes over 50,000-120,000 psig.

----
<b>Wrap up</b>

So what does this all mean?

s = My/I

s is dah stress.  Usually you use greek for this symbol, but this is a wiki.
M is the moment.  Kiki and Scott balancing is 800 ft-lbs.
y is the distance from the nutral axis.
I is the section modulus.

For a various cross sections:

Square:    I = d^4/12.
Rectangle: I = bh^3/12.
Circle: 

Note the evil fourth power terms.  This is what is important!  It means the following.

#Double the size and you increase stiffness 16 times.
#Double the thickness and you increase stiffness 8 times.
#Using hollow sections is vastly more effecient than solid sections.

Lastly!  There is a simple formula that one can use to find the section modulus when a section is offset from the central axis.

I = Ix + Ay^2.

Where Ix is the section mudulus of a section.  A is area and y is again the distance from the neutral axis.  This is useful when the section you are using is made up of several primitives.

Links
----
[http://www.efunda.com](http://www.efunda.com)
[http://physics.uwstout.edu/StatStr/statics/Beams/beam41.htm](http://physics.uwstout.edu/StatStr/statics/Beams/beam41.htm)


