pgtunepy3
=========

pgtunepy3 is a version of pgtune ported to be compatible with Python 3
(without breaking Python 2.x support) by Mark Nenadov and is available 
on GitHub.

pgtune "takes the wimpy default postgresql.conf and expands the database 
server to be as powerful as the hardware it's being deployed on". It is
written by Greg Smith gsmith@gregsmith.com

This branch is based on pgtune-0.9.3. The README provided here is largely 
from the original pgtune-0.9.3 archive.

Installation/Usage
==================

Source installation
-------------------

There is no need to build/compile pgtunepy3, it is a Python script.
Extracting tarball to a convenient location is sufficient. 

If your installation of Python is not in /usr/bin/python, you will need to
edit the first line of pgtunepy3

If you already have an installation of pgtune, you can simply overwrite
your existing /usr/bin/pgtune with pgtunepy3.


Using pgtune
============

pgtune works by taking an existing postgresql.conf file as an input,
making changes to it based on the amount of RAM in your server and
suggested workload, and output a new file.

Here's a sample usage::

  pgtune -i $PGDATA/postgresql.conf -o $PGDATA/postgresql.conf.pgtune

pgtune --help will give you additional usage information.  These
are the current parameters:

 * -i or --input-config : Specifies the current postgresql.conf file.

 * -o or --input-config : Specifies the file name for the new 
   postgresql.conf file.

 * -M or --memory: Use this parameter to specify total system memory. If 
   not specified, pgtune will attempt to detect memory size.

 * -T or --type : Specifies database type. Valid options are:
   DW, OLTP, Web, Mixed, Desktop

 * -c or --connections: Specifies number of maximum connections expected.
   If not specified, it depends on database type.

 * -D or --debug : Enables debugging mode. 

 * -S or --settings: Directory where settings data files are located at.
   Defaults to the directory where the script is being run from.  The
   RPM package includes a patch to use the correct location these
   files were installed into.

License
=======

pgtune (and also pgtunepy3) is licensed under a standard 3-clause BSD license.

Here is pgtune's original license:

Copyright (c) 2009, Gregory Smith
All rights reserved.

Redistribution and use in source and binary forms, with or without 
modification, are permitted provided that the following conditions are 
met:

  * Redistributions of source code must retain the above copyright 
    notice, this list of conditions and the following disclaimer.
  * Redistributions in binary form must reproduce the above copyright 
    notice, this list of conditions and the following disclaimer in 
    the documentation and/or other materials provided with the 
    distribution.
  * Neither the name of the author nor the names of contributors may 
    be used to endorse or promote products derived from this 
    software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS 
IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED 
TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A 
PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT 
HOLDER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, 
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, 
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY 
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE 
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

