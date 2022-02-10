![logo](https://fastnetmon.com/wp-content/uploads/2018/01/cropped-new_logo_3var-e1515443553507-1-300x146.png)

Community Edition
===========
FastNetMon - A high performance DoS/DDoS load analyzer built on top of multiple packet capture engines (NetFlow, IPFIX, sFlow, AF_PACKET, Netmap, PCAP).

What do we do?
--------------
We detect hosts in the deployed network sending or receiving large volumes of traffic, packets/bytes/flows, per second and
perform a configurable action to handle that event. These configurable actions include notifying you, switching off the server, or blackholing the client.

Flow is one or more ICMP, UDP, or TCP packets which can be identified via their unique src IP, dst IP, src port, dst port, and protocol fields.

Integration with flow systems
-----------------------------
At a very high level integration with FastNetMon is fairly simple. In both cases the work flow is the same and the main difference being the port numbers provided. The port numbers are configurable.

#### sFlow
Configure the IP of the server running FastNetMon using port 6343. This port number is configurable.

#### Netflow
Configure the IP of the server running FastNetMon using port 2055. This port number is configurable.

License: GPLv2

Official [mirror at GitLab](https://gitlab.com/fastnetmon/fastnetmon)

Project 
-------
- [Official site](https://fastnetmon.com)
- [FastNetMon Advanced, Commercial Edition](https://fastnetmon.com/fastnetmon-advanced/)
- [FastNetMon Advanced and Community difference table](https://fastnetmon.com/compare-community-and-advanced/)
- Detailed reference in Russian: [link](https://fastnetmon.com/wp-content/uploads/2017/07/FastNetMon_Reference_Russian.pdf)

Official support groups:
-------
- [Mailing list](https://groups.google.com/forum/#!forum/fastnetmon)
- [Slack](https://join.slack.com/t/fastnetmon/shared_invite/MjM3NDUwNzY4NjA5LTE1MDQ4MzE5NTAtYmU4MjYyYWNiZQ)
- IRC: #fastnetmon at irc.freenode.net [web client](https://webchat.freenode.net/)
- Telegram: [fastnetmon](https://t.me/fastnetmon)

Follow us at social media:
-------
- [Twitter](https://twitter.com/fastnetmon)
- [LinkedIn](https://www.linkedin.com/company/fastnetmon/)
- [Facebook](https://www.facebook.com/fastnetmon/)

Supported packet capture engines
--------------------------------
- NetFlow v5, v9
- IPFIX
- ![sFlow](http://sflow.org/images/sflowlogo.gif) v4, v5
- PCAP
- AF_PACKET
- Netmap
- SnabbSwitch (experimental) 
- PF_RING / PF_RING ZC (obsoleted, not recommented, please use AF_PACKET instead) 

You can check out the [comparison table](https://fastnetmon.com/docs/capture_backends/) for all available packet capture engines.

Complete integration with the following vendors 
--------------------------------
- [Juniper integration](src/juniper_plugin)
- [A10 Networks Thunder TPS Appliance integration](src/a10_plugin)
- [MikroTik RouterOS](src/mikrotik_plugin) Please use only recent versions of RouterOS!

Features
--------
- Detects DoS/DDoS in as little as 1-2 seconds
- Scales up to terabits on single server (sFlow, Netflow, IPFIX) or to 40G + in mirror mode
- Trigger block/notify script if an IP exceeds defined thresholds for packets/bytes/flows per second
- [Complete support](https://fastnetmon.com/docs/detected_attack_types/) for most popular attack types
- Thresholds can be configured per-subnet basis with the hostgroups feature
- [Announce blocked IPs](https://fastnetmon.com/docs/exabgp_integration/) via BGP to routers with [ExaBGP](https://github.com/Exa-Networks/exabgp) or  [GoBGP](https://fastnetmon.com/docs/gobgp-integration/)
- Full integration with [Graphite](https://fastnetmon.com/docs/graphite_integration/) and [InfluxDB](https://fastnetmon.com/docs/influxdb_integration/)
- [API](https://fastnetmon.com/docs/fastnetmon-community-api/) (available in master branch only)
- [Redis](https://fastnetmon.com/docs/redis/) integration
- [MongoDB](https://fastnetmon.com/docs/mongodb/) integration
- Netmap support (wire speed processing; only Intel hardware NICs or any hypervisor VM type)
- Filter NetFlow v5 flows or sFlow packets with LUA scripts (useful for excluding particular ports)
- Supports L2TP decapsulation, VLAN untagging in mirror mode 
- Complete plug-in support
- Capture attack fingerprints in PCAP format
- Experimental [BGP Flow Spec support](https://fastnetmon.com/docs/bgp_flow_spec/), RFC 5575

Running Fastnetmon
------------------
### Supported platforms
- Linux (Debian, CentOS, Ubuntu), x86_64 only
- FreeBSD: [official port](https://www.freshports.org/net-mgmt/fastnetmon/).

### Hardware requirements
- At least 1 GB of RAM

### Router integration instructions
- [Juniper MX Routers](https://fastnetmon.com/docs/junos_integration/)

### Distributions supported
- [Automatic install script for Debian/Ubuntu/CentOS](https://fastnetmon.com/install/)
- We are part of the [official FreeBSD ports collection](https://freshports.org/net-mgmt/fastnetmon/)
- [Docker image](https://fastnetmon.com/fastnetmon-community-docker-install/)


Screenshots
------------

Main program:

![Main screen image](docs/images/fastnetmon_screen.png)

Example CPU load on Intel i7-2600 with Intel X540/82599 NIC at 400Kpps load:
![Cpu consumption](docs/images/fastnetmon_stats.png)

Example deployment scheme:
![Network diagramm](docs/images/deploy.png)

Example of [notification email](https://fastnetmon.com/docs/attack_report_example/) about detected attack:

Author: [Pavel Odintsov](http://uk.linkedin.com/in/podintsov/)
