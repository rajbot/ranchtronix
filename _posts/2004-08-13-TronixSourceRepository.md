---
author: McCabe
date: '2004-08-13 07:37:51'
layout: post
title: TronixSourceRepository
---

## Tronix source repository

We have a [Subversion](http://subversion.tigris.org) source repository.

It can be viewed on the web at [http://svnhosting.org:8000/websvn/listing.php?repname=ranchtronix](http://svnhosting.org:8000/websvn/listing.php?repname=ranchtronix).

To check it out, you'll need a subversion client.

* [TortoiseSVN](http://tortoisesvn.tigris.org/) for Windows - it integrates with the windows shell.
* * To check out the repository, (after installing and restarting,) right click in the folder you want to create it in and choose 'checkout...'
* * Enter 'http://svnhosting.org:8000/svn/ranchtronix/' in 'URL of Repository'
* * In the directory that's created, right click on anything for lots of options.

* The command-line 'svn' client.
* * A Windows [installer](http://subversion.tigris.org/files/documents/15/14958/svn-1.0.6-setup.exe)
* * [Cygwin](http://cygwin.org) comes with a 'svn' - though you may need to choose to install it at setup time.  It's 'subversion' in the 'Devel' group.
* * Many other OSes at [http://subversion.tigris.org/project_packages.html,](http://subversion.tigris.org/project_packages.html,) including OS X.
* * To check out the repository...
* * 'svn checkout [http://svnhosting.org:8000/svn/ranchtronix'](http://svnhosting.org:8000/svn/ranchtronix')

Docs at [http://svnbook.red-bean.com/](http://svnbook.red-bean.com/) ...

Mini-tutorial or pointers thereto coming soon.  Checkin info too.
