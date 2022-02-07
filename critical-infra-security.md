### Security of Critical infrastructure

Some key areas to enable a secure, connected critical infrastructure:
* Enabling methodologies for communicating between a combination of trusted, untrusted, and adversarial networks as well as trusted, untrusted, and potentially adversarial equipment.
* Develop policy, guidelines, and suggestions for inspecting and whitelisting communications involving critical infrastructure including but not limited to ICS, SCADA, OT, and IoT.
* Deterministic timelines of security and functionality software/firmware updates to critical infrastructure 
* Making available innovative, trusted architectures

### Cybersecurity Maturity Model Certification (CMMC)
By developing the Cybersecurity Maturity Model Certification (CMMC), it is possible to normalize and standardizes cybersecurity preparedness. CMMC removes the disadvantages of a cybersecurity investment and requires an independently certified maturity level with well-defined guidelines in order to participate in certain acquisitions or to supply certain types of goods. This is good for cybersecurity because it reduces competitive threat from poorly secured Original Equipment Manufacturers (OEMs) and incentivizes positive security behaviors.

### Network segmentation
To mitigate risks from potentially compromised equipment, it is best to assume that it is compromised already but it needs to be used regardless. The most common approach adopted is widespread physical network segmentation.
In network segmentation , you are seperating various devices into multiple subnets and blocking packet routing across the gateway. By enforcing this, you are limiting attackers from propagating laterally to additional targets.
Generally, network segmentation is achieved by logically dividing the devices into small subnets and placing a Next-Generation Firewall (NGFW) at the gateway, and only allowing approved communications (port, protocol, application, and recipient) to pass.
Another type of network segmentation is physical separation, or “air-gapping”, where a set of subnets operates on a separate network that cannot be routed in or out of. This is widely used in national defense and nuclear applications because it makes the execution of zero-day exploits exponentially more difficult.

### Traffic inspection
It's important to build traffic inspection mechanism(s) in the critical networks to capture unknown traffic patterns.
Although implementing physical network segmentation is often recommended approach, it has its pros and cons - it keeps bad things out; but it keeps good things out as well. ICS and OT network need to be able to pass information such as control instructions and operating metrics. Further, technicians and engineers need to be
able to perform maintenance.

To move this data across the air-gap, sometimes a data diode is used. A data diode passes data in one direction only and it cannot be reversed. Although diodes help get data across the gap, they are simple devices; they don’t check to make sure it’s valid data and there are no policy violations.
To overcome these limitations, the concept of data guard is introduced. Data guards inspect the traffic moving between 2 or more airgapped networks and provide byte-level deep content inspection, data validation and filtering that can be tailored to customer-specific security policies, requirements, and risks. 

With strong traffic inspection and enforcement across the air-gap, it's possible to eliminate major vectors of attacks.

### References:
* https://securitydelta.nl/media/com_hsd/report/246/document/HSD-Rapport-Data-Diodes.pdf
* https://www.zadara.com/wp-content/uploads/AirGap_Arrosoft_Solution_Brief.pdf
