Description
===========

Installs and configures Graphite http://graphite.wikidot.com/

Requirements
============

Should run on CentOS 5+, RedHat etc.

Tested On
=========

* Tested on Amazon Linux 64-bit (AMI:ami-f9231b8d).

Attributes
==========

* `node[:graphite][:password]` sets the default password for graphite "root" user.

Usage
=====

`recipe[graphite]` should build a stand-alone Graphite installation.

`recipe[graphite::ganglia]` integrates with Ganglia. You'll want at
least one monitor node (i.e. recipe[ganglia]) node to be running
to use it.

Caveats
=======

Ships with two default schemas, stats.* (for Etsy's statsd) and a
catchall that matches anything. The catchall retains minutely data for
13 months, as in the default config. stats retains data every 10 seconds
for 6 hours, every minute for a week, and every 10 minutes for 5 years.
