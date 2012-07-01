kestrel-collectd-plugin
=======================

A [Kestrel](https://github.com/robey/kestrel) plugin for [collectd](http://collectd.org) using collectd's [Python plugin](http://collectd.org/documentation/manpages/collectd-python.5.shtml).

Data captured includes everything listed in: https://github.com/robey/kestrel/blob/master/docs/guide.md

Install
-------
 1. Place kestrel.py in /opt/kestrel-collectd (assuming you have collectd installed to /opt/collectd).
 2. Configure the plugin (see below).
 3. Restart collectd.

Configuration
-------------
Add the following to your collectd config.

    <LoadPlugin "python">
      Globals true
    </LoadPlugin>

    <Plugin "python">
      ModulePath "/opt/kestrel-collectd"

      Import "kestrel"

      <Module "kestrel">
        Host "localhost"
        Port 22133
        Verbose false
      </Module>
    </Plugin>

Requirements
------------
 * collectd 4.9+