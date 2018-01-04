### ICMP codes
**Code**|**Description**|**References**
:-----:|:-----:|:-----:
0|Network unreachable error|RFC 792
1|Host unreachable error|RFC 792
2|Protocol unreachable error Sent when the designated transport protocol is not supported|RFC 792
3|Port unreachable error|Sent when the designated transport protocol is unable to demultiplex the datagram but has no protocol mechanism to inform the sender
4|The datagram is too big|Packet fragmentation is required but the DF bit in the IP header is set
5|Source route failed error|RFC 792
6|Destination network unknown error|RFC 1122
7|Destination host unknown error|RFC 1122
8|Source host isolated error (Obsolete)|RFC 1122
9|The destination network is administratively prohibited|RFC 1122
10|The destination host is administratively prohibited|RFC 1122
11|The network is unreachable for Type Of Service|RFC 1122
12|The host is unreachable for Type Of Service|RFC 1122
13|Communication Administratively Prohibited.This is generated if a router cannot forward a packet due to administrative filtering|RFC 1812
14|Host precedence violation.Sent by the first hop router to a host to indicate that a requested precedence is not permitted for the particular combination of source/destination host or network| upper layer protocol
15|Precedence cutoff in effect.The network operators have imposed a minimum level of precedence required for operation| the datagram was sent with a precedence below this level
16-255| Not assigned|	 
