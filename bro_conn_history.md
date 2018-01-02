### Connection history 

**Letter**|**Meaning**
:-----:|:-----:
s|SYN w/o the ACK bit set
h|SYN+ACK ("handshake")
a|pure ACK
d|packet with payload ("data")
f|packet with FIN bit set
r|packet with RST bit set
c|packet with a bad checksum
t|packet with retransmitted payload
i|inconsistent packet (e.g. FIN+RST bits set)
q|multi-flag packet (SYN+FIN or SYN+RST bits set)
^|connection direction was flipped by Bro's heuristic
