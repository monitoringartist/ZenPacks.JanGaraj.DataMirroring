================================================
ZenPacks.JanGaraj.DataMirroring (beta) - code it
================================================

About
=====

This ZenPack is not standard Zenpack Install&Use. It provides only example code to mirror Zenoss data into another (monitoring) systems. 
It's monkey patch for Products.ZenRRD.RRDUtil.RRDUtil.save() method, so you have to be 100% sure about your ZenPack code. 
Mirror tasks are executed in new threads and they don't block Zenoss RRDUtil code. It depends on your requirements, but 
probably you will need to implement some performance improvements (persistent connections/connection pool/...) for serious production service.
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

You want to test some cool feature (graphing/anomaly detection/analyzing/reporting/alerting) of another system, but you don't want to make full installation.
So you can mirror current data from Zenoss to another system and you can test it.   
                                
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
zenpack --install ZenPacks.JanGaraj.DataMirroring-0.0.1.egg
zenoss restart
```
        

Developer Installation (link mode)
----------------------------------

If you wish to further develop and possibly contribute back to the DataMirroring
ZenPack you should clone the [git repository](https://github.com/jangaraj/ZenPacks.JanGaraj.DataMirroring.git),
then install the ZenPack in developer mode using the following commands.

```
git clone git://github.com/jangaraj/ZenPacks.JanGaraj.DataMirroring.git
zenpack --link --install ZenPacks.JanGaraj.DataMirroring
zenoss restart
```  

Thanks
======

- [Zenoss](http://www.zenoss.com/) - send your appreciation to Zenoss guys via Andrew D Kirch AKA trelane (Zenoss community manager) 
- Cluther - thanks for snippet https://gist.github.com/cluther/4ba4debaab5bdb72147d
- [Jan Garaj](http://www.jangaraj.com/) - endorse me for Zenoss/Zabbix skill on [Jan Garaj LinkedIn](https://www.linkedin.com/in/jangaraj)
