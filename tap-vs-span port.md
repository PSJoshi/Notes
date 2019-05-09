### Taps vs Span ports
There are two common methods to extract traffic directly from the system: TAPs and SPANs. A network TAP is a hardware component that connects into the cabling infrastructure to copy packets for monitoring purposes. A SPAN (Switch Port ANalyzer) is a software function of a switch or router that duplicates traffic from incoming or outgoing ports and forwards the copied traffic to a special SPAN (or sometimes called mirror) port. In general, network TAPs are preferred over SPAN ports for the following reasons:

* SPAN ports are easily oversubscribed and have the  lowest priority when it comes to forwarding, which results in dropped packets
* The SPAN application is processor-intensive and can have a negative performance impact on the switch itself, possibly affecting network traffic
* Because SPAN traffic is easily reconfigured, SPAN output can change from day to day, resulting in inconsistent reporting

However, there are some situations where inserting a TAP is not practical. For example, traffic could be running on a physical infrastructure outside your direct control, or maintenance windows may not allow for timely TAP deployments. Perhaps a remote location may not be able to justify a permanent TAP, but has SPAN access for occasional troubleshooting needs since a SPAN can be added without bringing down a link.

### Passive Taps
A passive TAP requires no power of its own and does not actively interact with other components of the network. It uses an optical splitter to create a copy of the signal and is sometimes referred to as a “photonic” TAP. Most passive TAPs have no moving parts, are highly reliable and do not require configuration.

### Active taps
Active TAPs are not passive. They require their own power source to regenerate the signals. There is no split ratio consideration because the TAP receives the message and then retransmits it to both the network and monitoring destinations. From a highlevel perspective this would appear to be a positive feature. Even so, passive TAPs are preferred. During a power outage, an active TAP cannot regenerate the signal, so it becomes a point of failure. Since a passive TAP is not powered, it would be unaffected during a power outage and the packets (originating from a source that still has power) would continue to flow.

* Ref - https://www.gigamon.com/content/dam/resource-library/english/white-paper/wp-network-taps-first-step-to-visibility.pdf


