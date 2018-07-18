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
