---
author: Mang
date: '2005-11-08 03:24:51'
layout: post
title: MangResearchKernelShaikhCornford
---

Clippings from paper on CVS/BK hosted by the Open Source Research Community at MIT.

"Version Management Tools: CVS to BK in the Linux Kernel"
[http://opensource.mit.edu/papers/shaikhcornford.pdf](http://opensource.mit.edu/papers/shaikhcornford.pdf)

'''CVS (basically all or nothing push write access) doesn't match Linus' trust model:'''

Still Linus was quite adamant about his refusal to use CVS officially and the public repository feature of CVS made him shudder, I don't like the idea of having developers do their own updates in my kernel source tree. I know that's how others do it, and maybe I'm paranoid, but there really aren't that many people that I trust enough to give write permissions to the kernel tree [31]. Trust is a key feature of the OS process, the deterioration of which could lead to a breakdown of the community and process. Linus dropping patches was creating uncertainty


CVS, it was noted, had caused security breakdowns within FreeBSD and OpenBSD and Miller, of all people in May 1997, had claimed that CVS use was the worst feature of the *BSD projects and is one of the numerous reasons behind the personal and political problems they have. This strategy leads to power struggles and political problems [21]. So not only were there security concerns but CVS was seen as leading to political struggles because it allowed many people to submit patches to the official software tree and thus questions of whose patch will get accepted became prolific. Wilson [37] suggested that CVS is 10 years behind equivalent commercial offerings in which case Linuss decision to not use CVS maybe understandable. Linus wanted to avoid more pressures plus he believed that CVS allow[ed] automatic acceptance of patches, and positively _encourage_ people to "dump" their patches on other people, and not act as real maintainers


'''This isn't really apropos, but it's a great quote from RMS in 2002 on the licensing terms of BK (and turned out to be quite right):'''

The spirit of the Bitkeeper license is the spirit of the whip hand. It is the spirit that says, "You have no right to use Bitkeeper, only temporary privileges that we can revoke
. Outrage at this spirit is the reason for the free software movement
