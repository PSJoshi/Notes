### Explanation of Flows vs Connection vs Session
A network flow is defined as unidirectional sequence of packets between two network 
endpoints and have the following attributes:
* Source IP
* Destination IP
* Protocol
* Source Port
* Destination Port 
* Type of service (ToS)
* Input interface

Whereas connection is simply a bidirectional flow (a forward flow and a reverse flow)

In a session, you will have many connections between same source and destination. In addition, routing 
policies, paths followed by packets in flows and sessions are different as explained below:

IP routing is stateless and routes each packet based on the IP address and port. A stateless 
connection is one in which no information is retained by either sender or receiver. TCP is used
to manage state and is managed by the end servers. Firewalls are stateful and keep track of 
TCP/UDP sessions. The firewall tracks the attributes of the session such as sequence numbers 
and keeps this information in dynamic state tables. Load balancers and WAN Optimizers are 
added to networks to manage the state of a session to solve the problem of stateless routers.

 IP routing creates a fixed path between two networks. While routes can change based on network
 outages, it is not possible to dynamically route a flow over multiple paths in a stateless 
 network. Flows are packet based whereas sessions are services/application based. In a flow, 
 all packets that are alike, are treated the same. For instance, if there are six concurrent 
 cloud based video streams, the router will treat all the UDP packets the same once the flow 
 is established. Session based networking allows each session to be dynamically treated 
 different such as priority and bandwidth shaping.
 
 ### Credits:
 * https://talkingpointz.com/flows-vs-sessions/

## Netflow traffic classification using netflow

### Name: Good traffic
* Class: Good
* Score:10
* Note: A list of known hosts/netblocks extracted from nDPI source code e.g. netblock of google, twitter etec.

### Name: Alienvault Bad IP
* Class: Bad
* Score:10
* Note: IP addresses from Alienvault threat intelligent database is used to flag malicious flows.

### Name: Emerging threats Bad IP
* Class: Bad
* Score: 10
* Note: IP addresses from Emerging threats feed is used to flag malicious flows. 

### Name: Insecure TCP ports
* Class: Bad
* Score: 10
* Note: Any traffic flow that included traffic to a list of TCP or UDP ports for insecure protocols -e.g. telnet,ftp, rsh

### Name: Unknown port conversation
* Class:Bad
* Score:10
* Note: Any traffic flow between unknown or un-assigned source and destination TCP or UDP ports is flagged as anomaly.

### Name:SYN_Flood
* Class:Bad
* Score:10
* Note: Any traffic flow that contains only SYN packet is treated as malicious.

### Name: SSH Brute Force scan
* Class:Bad
* Score:20
* Note: Any flows to port 22 having 11 to 51 packets in flow is treated as possible SSH Brute force attack.

### Name: Possible TCP SCAN
* Class: Bad
* Score: 20
* Note: For thie test, flows are grouped by destination port and counted along with average number of packets per flow. Any group with more than 1000 flows and less than 4 packets per flow is considered to indicate possible scanning of destination port associated with the group. The reasoning is that a large number of flows to a port with very few packets per flow is an indication of scanning attempt.
