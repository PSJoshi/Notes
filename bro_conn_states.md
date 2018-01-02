**Connection state**|**Meaning**
:-----:|:-----:
S0|Connection attempt seen
S1|Connection established
SF|Normal establishment and termination. Note that this is the same symbol as for state S1. You can tell the two apart because for S1 there will not be any byte counts in the summary
REJ|Connection attempt rejected.
S2|Connection established and close attempt by originator seen (but no reply from responder).
S3|Connection established and close attempt by responder seen (but no reply from originator).
RSTO|Connection established
RSTR|Responder sent a RST.
RSTOS0|Originator sent a SYN followed by a RST
RSTRH|Responder sent a SYN ACK followed by a RST
SH|Originator sent a SYN followed by a FIN
SHR|Responder sent a SYN ACK followed by a FIN
OTH|No SYN seen
