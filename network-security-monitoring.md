### Network monitoring
It is a a system that constantly monitors a computer network for slow or failing systems and that notifies the network administrator in case of outages via email, pager or other alarms.

Network monitoring can be done in two ways:
* Active network monitoring
* Passive network monitoring

#### Active network monitoring
In active monitoring, a test traffic is injected onto the network and subsequent flows are monitored. This kind of monitoring is useful when you want data on patricular aspect of network performance e.g. latency between two end-points, packet-drops, jitter, analysis of malicious payloads and so on.

#### Passive monitoring
It's like a continuous observation of network traffic followed by its detailed studies.

Typically, instead of injecting artificial traffic onto your network, passive monitoring involves monitoring of traffic that is already on the network. This kind of monitoring requires a device on the network to capture network packets for analysis.  This can be done with specialized probes designed to capture network data or with built-in capabilities on switches or other network devices.  Passive network monitoring can collect large volumes of data and from that we can derive a wide range of information.  For example, TCP headers contain information that can be used to derive network topology, identify services and operating systems running on networked devices, and detect potentially malicious probes.

Through passive monitoring, a security admin can gain a thorough understanding of the network's health. Much of this data can be gathered in an automated, non-intrusive manner through the use of standard tools.Passive monitoring tools can record, analyze, correlate and produce highly valuable security intelligence specific to a network.

### Why Network security monitoring
Network security monitoring involves collecting the full spectrum of data types (event, session, full content and statistical) needed to identify and validate intrusions. The goal is to detect and respond to threats as early as possible to prevent data loss or disruption and restore the normalcy in operations. Often, this is complicated when mountains of security-related events and log data are continuously produced by multiple disparate security tools.

Most of the commercial products do generate useful security alerts ,say, "event X happened" but they do not provide enought context so that the user can act on it. The end users are always in dilemma whether the alert is relevant or not and in many cases, it is just overlooked/ignored. The usage of network security monitoring tools in open source domain allows security analyst to drill down the alerts to its minute details and make decisions.

Network security monitoring can be done in two ways:

### Active security monitoring
Active (in-line) monitoring typically includes “bump in the wire” type solutions –

* Firewalls/Proxies 
* Malware/Virus scanners (Spam, Phishing, Virus)
* Whitelisting / blacklisting at various layers
* Encryption/Man-in-the-middle

Active measures are good first steps but they are only as effective as the signature data and/or configuration driving them. Each organization’s traffic profile is different and a lot of times active measures are not sufficient or very effective and often, they go stale very quickly with the new attacks in the wild every day.

Most firewalls are configured to block or allow combinations of IP / port / protocol. There are next-gen firewalls that also do Deep packet inspection to block malicious IPs/URLs. Malware scanners depend on pre-configured patterns of known bad attachments or phishing URLs. Whitelisting / blacklisting rules need to be updated on a regular basis to be effective.

### Passive security monitoring
As indicated earlier, a passive monitoring system can be configured to parse a copy of live network traffic, flag known anomalies and take action(machine learning) or log it for a human(security admin) to look at. A good passive monitoring solution typically has following capabilities:
* Can keep up and watch all 7-layers of network traffic
* Can parse and de-construct connection flows on the fly
* Can log traffic meta-data for correlation
* Can apply pre-defined identification rules and flag off suspicious activities
* Support flexible configuration to define new patterns on the fly

There are several open source tools available for passive security monitoring and the most commomly used are described below:

#### Snort/Suricata:
Snort used to be the defacto IDS / IPS engine of choice for anyone looking to run an IDS.Suricata is another popular IDS project that allows efficient monitoring of very high speed links above 1Gbps. Snort / Suricata engines have a rich set of community and open/commercial rules sets available. It is possible to run it on an edge machine (router / firewall) or on a intranet machine to watch bad traffic that is flowing through and raise alerts.

#### Bro:
Bro is a general purpose traffic analysis platform that can also function as IDS!  Bro engine is driven by program like scripts that define patterns to be matched, ignored or alerted. Bro can run on commodity hardware and can be scaled up to 100Gbps.

### Wireshark

### Network Miner

### 
#### Useful presentations:
Principle of network security monitoring - https://www.mycert.org.my/mycert-sig/mycert-sig-08/slides/MyCERT-NSM-presentation.pdf

