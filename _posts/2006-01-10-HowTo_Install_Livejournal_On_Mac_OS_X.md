---
author: Raj
date: '2006-01-10 08:41:10'
layout: post
title: HowTo_Install_Livejournal_On_Mac_OS_X
---

Installing the Jan 2006 livejournal server on OS X Tiger 10.4.3.

Instructions here: [http://www.livejournal.com/doc/server/lj.install.index.html](http://www.livejournal.com/doc/server/lj.install.index.html)

### 6.2 Installing Perl Modules

* First, install mysql 5.0 using binary installer: [http://dev.mysql.com/downloads/mysql/5.0.html](http://dev.mysql.com/downloads/mysql/5.0.html)

* Start the mysql server: 
* * cd /usr/local/mysql
* * sudo ./bin/mysqld_safe

* Install DBD::mysql: sudo perl -MCPAN -e "install 'DBD::mysql'"

* sudo perl -MCPAN -e "install 'Image::Size'"
* sudo perl -MCPAN -e "install 'MIME::Lite'"

* Install libjpeg using these instructions and patched makefile: [http://www.kyngchaos.com/macosx/install/libjpeg.php](http://www.kyngchaos.com/macosx/install/libjpeg.php)

* Install libpng from here: [http://www.libpng.org/pub/png/libpng.html](http://www.libpng.org/pub/png/libpng.html)

* Install libgd
* * Download from [http://www.boutell.com/gd](http://www.boutell.com/gd)
* * ./configure --mandir=/usr/local/share/man --without-fontconfig --without-freetype
* * make; sudo make install
* * (turned off freetype because I didn't have it installed, turned off fontconfig because i heard bad things)

* (sudo perl -MCPAN -e "install 'GD'")

Test script to see what modules are already installed:

<pre>
#!/usr/bin/perl

use DBI;
use DBD::mysql;
use Digest::MD5;
use Digest::SHA1;
use Image::Size;
use MIME::Lite;
use MIME::Words;
use Compress::Zlib;
use MIME::Base64;
use URI::URL;
use HTML::Tagset;
use HTML::Parser;
use LWP::Simple;
use LWP::UserAgent;
use GD;
use Mail::Address;
use Unicode::MapUTF8;
use Storable;
use Time::HiRes;
use IO::WrapTie;
</pre>


