---
author: McCabe
date: '2004-08-13 21:29:28'
layout: post
title: MiniTutorial
---

## Subversion mini tutorial

    $ svn checkout [http://svnhosting.org:8000/svn/ranchtronix](http://svnhosting.org:8000/svn/ranchtronix)
    $ cd ranchtronix
    $ ls
    README  avr  index.html

    << create a test file >>
    $ cat > testfile.txt
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
    Authentication realm: <http://svnhosting.org:8000>; Subversion Repository
    Password for 'mike': <-- press enter here to get a chance to use a different username
    Authentication realm: <http://svnhosting.org:8000>; Subversion Repository
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
    $cat testfile.txt
    this

    is really not

    a big

    test
