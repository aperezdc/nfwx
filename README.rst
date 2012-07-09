==============================
NFWX - Nokia Firmware Explorer
==============================

NFWX is a small command-line tool to explore the available firmware
downloads for Nokia devices, which can be obtained using the same
SOAP services as used by the Nokia-supplied tools to install the
updates.


Disclaimers
===========

* This software **does not download any firmware/software from the Nokia
  servers**. It just provides a listing of what's available and the URLs
  to files.

* The software **is provided as-is, without warranty of any kind**.
  The author is not responsible for any damage which may be caused to
  your phone due to the incorrect usage of it.

* It is **recommended** to use the `official update procedures`__ for
  your Nokia devices.

__ http://www.nokia.com/global/support/software-update/update-your-phone/


Requirements
============

This tool is written in Python_, and uses the SOAPpy_ library.

.. _python: http://www.python.org
.. _soappy: https://github.com/tarequeh/SOAPpy


Usage
=====

Make sure you have Python_ and SOAPpy_ installed, then you can run the
tool in interactive mode (which is faster). It will show a ``(nfwx)``
prompt, where you can enter commands::

  % ./nfwx
  (nfwx) _

To get information about a particular command, use ``help``::

  (nfwx) help products
  List product-ids and their names.

Alternatively, commands can be entered directly from the shell when
invoking ``nfwx``::

  $ ./nfwx products > productlist.txt


Tips and tricks
===============

It is possible to pass a string to search inside the products list::

  (nfwx) products N9
  xxxxxxxxxx     Nokia N97 mini
  yyyyyyyyyy     Nokia N9
  ...

For scripting purposes, it is possible to define the environment variable
``NFWX_SID`` to the output of the ``sid`` command, to avoid each invocation
requesting a new session identifier to the web service::

  % export NFWX_SID=$(./nfwx sid)
  % ./nfwx variants 123456789
  ...
  % ./nfwx releases 666999666
  ...


How do I flash my device?
=========================

`Ask somewhere else`__. Seriously.

__ http://lmgtfy.com/?q=how+to+flash+a+nokia+phone


License
=======

This software is distributed under the terms of the `MIT license`__.

__ http://opensource.org/licenses/mit-license.php

