.. _munin:

.. program:: munin

=======
 munin
=======

DESCRIPTION
===========

Munin is a group of programs to gather data from hosts, graph them,
create html-pages, and optionally warn contacts about any off-limit
values.

Munin master
============

The Munin master contains the following command line programs:

Run from cron
-------------

* :ref:`munin-cron` to run other munin programs every 5 minutes. It is run from cron.
* :ref:`munin-update` to gather data from machines running munin-node. Usually run by
  :ref:`munin-cron`.
* :ref:`munin-limits` to check for any off-limit values. Usually run by :ref:`munin-cron`.
* :ref:`munin-graph` to create graphs from data contained in rrd-files. Usually run by
  :ref:`munin-cron` unless :option:`graph_strategy` is set to "cgi" in :ref:`munin.conf`.
* :ref:`munin-html` to draw html-pages on an Munin installation. Usually run by :ref:`munin-cron`
  unless :option:`html_strategy` is set to "cgi" in :ref:`munin.conf`.

Run from web server
-------------------
   
* :ref:`munin-cgi-html` is used to provide html pages on demand.
* :ref:`munin-cgi-graph` is used to provide graph images on demand.
* :ref:`munin-cgi-datafile` is used to provide metadata for nodes and plugins on json format.

Munin node
==========

The munin node consists of the following programs

Daemons
-------
* :ref:`munin-node` runs on all nodes where data is collected.
* :ref:`munin-asyncd` is a daemon that runs alongside a munin-node. It queries the local
  :ref:`munin-node`, and spools the results.

Command line scripts
--------------------

* :ref:`munin-node-configure` can automatically configure plugins for the local node.
* :ref:`munin-doc` outputs plugin documentation.
* :ref:`munin-run` runs a plugin with the same environment as if run from :ref:`munin-node`. Very
  useful for debugging.
* :ref:`munin-async` is a command line utility, known as an "asyncronous proxy node".
  :ref:`munin-update` can connect via ssh and run :ref:`munin-async` this to retrieve data from the
  munin async spool without waiting for the node to run plugins.

AUTHORS
=======

Jimmy Olsen, Audun Ytterdal, Brian de Wolf, Nicolai Langfeldt

SEE ALSO
========

:ref:`munin-update`, :ref:`munin-graph`, :ref:`munin-limits`,
:ref:`munin-html`, :ref:`munin.conf`,

