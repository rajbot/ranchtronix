---
author: Mang
date: '2005-10-27 16:53:40'
layout: post
title: MangAlgorithmicComposition
---

Autech-o-Matic

Autech-o-Matic is a system to generate music in the vein of the whacky rhythmic pieces by Autechre, Aphex Twin, or Squarepusher.  The rhythm has a consistent underlying logic but the individual sections sound pseudo-random.  The rhythm is very fast/intricate, so it seems like the perfect thing for a computer to generate.  The pieces have a fairly widespread appeal and having my dj friends like the output of my algorithms is my metric for success.

Phases of the project

* make a catalog of existing pieces that I like
* map out the rhythm and melody parts
* figure out what it is I like about them
* grab some appropriate samples
* write an algorithm to make music in this style
* * generate the individual drum sections (short patterns of very fast notes) (drum-hit algorithm)
* * generate entire bars (drum sequence algorithm)
* * generate an entire piece (3-4 minutes) (structure algorithm)
* make or find some input data that generates a pleasing final piece

The most likely candidate (that I know so far) for the algorithm is a set of markov chains.  I'd like to explore some different techniques and see what works best.  The input to the system will be a set of control data curves (as wave data).  Initially these will be synthetic curves generated algorithmically or by hand, but the idea is that I'll be able to feed in different data (e.g. EEG readings) and get results that aesthetically echo that data.
