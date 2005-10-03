---
author: Raj
date: '2005-10-03 21:51:57'
layout: post
title: HowTo_Backup_Your_Computer
---

## [HowTo](HowTo.html) backup your computer

My usualy advice is "use rsync", but Jesse gives some really good advice. I added a bit here and there.

As you can imagine, this is one of those topics that geeks take pride in
having long and serious arguments about.  Oh wait, that is just about
every geek topic (email clients, photo software etc).

So: some recommendations I have for backup workflow (This is just the way
I think about this kind of stuff)

* put all your files into one folder (Don't spread them all over the using Desktop, Documents, Music, Movies, Favorites, etc like the Mac tries to make you do).  This makes backups a lot easier.  on OSX, everything ends up in /Users/fur (for you).  So maybe that is good enough....depends what kind of granularity you want.

* separate your files into small important files (each file is on the order of kilobytes) and large less important files (each file is on the order of megabytes)

* I actually separate things into three groups: kilobytes, megabytes, and gigabytes, because I work with video that is in the gigabyte range and these require special handling

* Once you have your files separated like this, backing up is straighforward.  Your kilobyte files can be copied to:
* * Your unix account at UC (about the safest place in the world for data)
* * Burn to CD-ROM (if you have a burner)
* * Copy to a USB flash drive (cheap and reliable)
* * Copy to an external hard drive (I think you have one already)

* Your "on the order of megabytes" files can be copied to:
* * CD-ROM or DVD-ROM
* * an external hard drive

I recommend having at least three different copies.  For example having
two external hard drives and burning CDs.  Or you can use one external
hard drive, a USB flash drive, and burn CDs.

Finally, doing backups is mostly about personality and discipline.  I can
talk for hours about backup theory (and I help my mom with backups, etc).
But truth is I don't really do backups.  Raj is much better about actually
doing backups (I think).

Hard drives.  Hitachi and Seagate make the most reliable drives.  (Note
that given the strategies above, it shouldn't matter if the drive dies
because you have other backups.  But I still like to get good drives.)   I
would stay away from [MaxStor](MaxStor.html) and Western Digital.  Unfortunately with
[FireWire](FireWire.html) drives, it is often difficult to ascertain who manufactured the
drive that is actually in [FireWire](FireWire.html) enclosure (unless the enclosure is
branded).  So for example I get my external drives from [OtherWorld](OtherWorld.html)
Computing.  I don't know what drives they use, but I've had good
experiences:
[http://eshop.macsales.com/shop/firewire/fw400-USB2-combo-drives/](http://eshop.macsales.com/shop/firewire/fw400-USB2-combo-drives/)

Raj has told me he hates OWC and will never buy from them again...dunno
where he buys drives.

USB flash drives (the tiny ones) are cheap and pretty reliable.  Probably
physically more reliable than hard drives, but they are easier to lose
since they are so tiny.

Retrospect and Backup Software: I generally stay away from "backup
software" because in the rare event that I do a backup, I want to know
exactly what is going on with my files.  But that's just the way I am, a
lot of people use Retrospect.  My general idea with backups is to keep
lots of copies of small important files around and understand that if my
hard drive crashes I will have to spend a few days rebuilding my system.
With Retrospect, you might not have to go through that pain (I don't know
for sure).  You may also want to look at something called Carbon Copy
Cloner.
[http://www.bombich.com/software/ccc.html](http://www.bombich.com/software/ccc.html)

It's a free program that can clone your entire internal hard drive to an
external firewire drive.  This means you can actually boot up your
powerbook from the extern firewire drive and basically continue computing
along as if nothing happened (except of course that there is now this
brick of an external hard drive connected to you powerbook):

So there you go.  Simple, right? :-)
