ZenPacks.JanGaraj.DataMirroring
===============================

About
=====

This ZenPack is not standard Zenpack Install&Use. It provides only example code 
to mirror Zenoss data into another (monitoring) systems. It's monkey patch for 
Products.ZenRRD.RRDUtil.RRDUtil.put() method, so you have to be 100% sure about 
your ZenPack code. Mirror tasks are executed in new threads and they don't block 
Zenoss RRDUtil code. It depends on your requirements, but probably you will need 
to implement some performance improvements (persistent connections/connection 
pool/...) for serious production service. Keep in mind also concurrency and 
timeouts problems in your code.

Please donate to author, so he can continue to publish other awesome projects 
for free:

[![Paypal donate button](http://jangaraj.com/img/github-donate-button02.png)]
(https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=8LB6J222WRUZ4)

Example codes are provided for mirroring to:

- Carbon (Graphite)/Dataloop/InfluxDB
- Horizon (Skyline)
- OpenTSDB
- collectd
- Zabbix
- MySQL/MariaDB
- file

Use case
========

You want to test some cool feature (graphing/anomaly detection/analyzing/reporting/alerting) 
of another system, but you don't want to make full installation. You can realtime 
mirror current data from Zenoss to another system and you can test it.   
                                
Requirements
============

Zenoss
------

You must first have, or install, Zenoss 4. This ZenPack was tested
against Zenoss 4.2.5. You can download the free Core
version of Zenoss from http://community.zenoss.org/community/download.

Installation
============

Normal Installation (packaged egg)
----------------------------------

Download the ZenPack code, edit __init__.py file and create your own egg file.
Copy this file to your Zenoss server and run the following commands as the zenoss
user.

```
zenpack --install ZenPacks.JanGaraj.DataMirroring-1.0.0.egg
zenoss restart
```
        

Developer Installation (link mode)
----------------------------------

If you wish to further develop and possibly contribute back to the DataMirroring
ZenPack you should clone the [git repository]
(https://github.com/monitoringartist/ZenPacks.JanGaraj.DataMirroring.git), then install 
the ZenPack in developer mode using the following commands.

```
git clone git://github.com/monitoringartist/ZenPacks.JanGaraj.DataMirroring.git
zenpack --link --install ZenPacks.JanGaraj.DataMirroring
zenoss restart
```  

Author
======

[Devops Monitoring zExpert](http://www.jangaraj.com), who loves monitoring 
systems, which start with letter Z. Those are Zabbix and Zenoss.

Professional monitoring services:

[![Monitoring Artist](http://monitoringartist.com/img/github-monitoring-artist-logo.jpg)]
(http://www.monitoringartist.com)
