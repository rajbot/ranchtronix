---
author: McCabe
date: '2004-08-13 21:24:51'
layout: post
title: TronixSourceRepository
---

## Tronix source repository

We have a [Subversion](http://subversion.tigris.org) source repository.

It can be viewed on the web at [http://svnhosting.org:8000/websvn/listing.php?repname=ranchtronix](http://svnhosting.org:8000/websvn/listing.php?repname=ranchtronix).

To check it out, you'll need a subversion client:

* [TortoiseSVN](http://tortoisesvn.tigris.org/) for Windows - it integrates with the windows shell.
* * To check out the repository, (after installing and restarting,) right click in the folder you want to create it in and choose 'checkout...'
* * Enter 'http://svnhosting.org:8000/svn/ranchtronix/' in 'URL of Repository'
* * In the directory that's created, right click on anything for lots of options.

... or:

* The command-line 'svn' client.
* * A Windows [installer](http://subversion.tigris.org/files/documents/15/14958/svn-1.0.6-setup.exe)
* * [Cygwin](http://cygwin.org) comes with a 'svn' - though you may need to choose to install it at setup time.  It's 'subversion' in the 'Devel' group.
* * Many other OSes at [http://subversion.tigris.org/project_packages.html,](http://subversion.tigris.org/project_packages.html,) including OS X.
* * To check out the repository...
* * 'svn checkout [http://svnhosting.org:8000/svn/ranchtronix'](http://svnhosting.org:8000/svn/ranchtronix')

Docs at [http://svnbook.red-bean.com/](http://svnbook.red-bean.com/) ...

Mini-tutorial:

<nowiki>
$ svn checkout [http://svnhosting.org:8000/svn/ranchtronix](http://svnhosting.org:8000/svn/ranchtronix)
$ cd ranchtronix
$ ls
README  avr  index.html

<< create a test file >>
$cat > testfile.txt
this
  
is
 
a

test

<< subversion doesn't know about it yet >>

$ svn stat testfile.txt

?      testfile

<< tell subversion about it >>

<< note that this doesn't touch the repository yet >>

$ svn add testfile.txt

A         testfile.txt

<< commit it to the repository.  At this point svn may ask you for a username/password >>

$ svn commit testfile.txt --message "Initial checkin"
Adding         testfile.txt
Authentication realm: <http://svnhosting.org:8000> Subversion Repository
Password for 'mike': <-- press enter here to get a chance to use a different username
Authentication realm: <http://svnhosting.org:8000> Subversion Repository
Username: mccabe
Password for 'mccabe': <password here>
Transmitting file data .
Committed revision 11.

<< change testfile.txt >>
$ cat > testfile.txt
this

is really not

a

test

<< Ask subversion what's different >>
<< NOTE this still doesn't touch the repository >>
$ svn diff testfile.txt
Index: testfile.txt
===================================================================
--- testfile.txt        (revision 11)
+++ testfile.txt        (working copy)
@@ -1,6 +1,6 @@
    this
 
-is
+is really not
 
    a

<< commit my changes to the repository >>
$ svn commit testfile.txt --message "Amend intentions"
Sending        testfile.txt
Transmitting file data .
Committed revision 12.

<< At this point, somebody else makes some changes. >>

$ svn up testfile.txt 
U  testfile.txt
Updated to revision 13.
mccabe ~/s/ranchtronix:cat testfile.txt
this

is really not

a big

test

</nowiki>
