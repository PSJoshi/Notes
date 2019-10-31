## Blue team tips

### Network diagram

A good network diagram that presents a high level overview of network including ingress/egress points across all sites is a MUST and should include:

* All routing devices, proxies or gateways that affect flow of traffic
* External/Internal IP addresses of routing devices, proxies and gateways
* Workstations, servers or other devices - IP address ranges, custom groupings

Scan the network using nmap and build your attack surface. Find also vulnerabilities associated with the services using nmap plugins.

### Control Local Admin account
Microsoft's local administrator password solution(Microsoft LAPS) should be used. If you have a single admin password for every machine, it's easy to compromise all the machines in lateral movement stage once the attacker is in the network. LAPS will create a unique admin password for each endpoint and is securely stored and managed in Active directory environment. However, it requires agent installation and GPO creation.

### Gain visibility in powershell execution
Powershell has become a de-facto standard for attackers for penetration in any network. Some of the popular exploit frameworks are Powersploit, Empire, Nishang, PoshC2 and many others. Powershell comes by default in all Windows installation now a days and it makes the attackers job easy. On the top of it, no logging by default is enabled in Windows.
So, as a defender, you have to enable powershell logging to gain visibility. But, it is enabled only in Powershell Ver 5 onwards and allows powershell module logging, scriptblock logging(input/output commands) and automatic suspicious script detection. It also de-obfuscates encoded powershell commands. The powershell logging results in windows event log codes in the range 400-4xx.

### Track process creation
Tracking process execution is the key for anything malicious infecting the system(s) or running on the system(s). Process creation logging generates event ID 4688.

### Advanced system logging with Sysmon
SysMon provide more information about parent process, file hashes, network connection, loading of DLLs/drivers etc. On the top of it, it's a free tool from Microsoft and every organization should have deployed this tool in their environment.

### Visualization of active directory environment
In windows environment, it is essential to keep track of attack paths to domain controller and bloodhound is the tool you should definitely go for - https://github.com/BloodHoundAD/BloodHound 
It gives information like:

### Active directory defense
You should definitely follow recommendations by Sean Metcalf available at https://adsecurity.org/?p=1684

### Audit endpoint
It is recommended to audit the endpoint using CIS benchmarks or "HardeningAuditor" tool - https://github.com/cottinghamd/HardeningAuditor
Also, Australian signals directorate has a great guide on Windows hardening - https://www.asd.gov.au/publications/protect/Hardening_Win10.pdf
Please go through it carefully.

If you wish, there are many good tips available here - 
https://www.sneakymonkey.net/2018/06/25/blue-team-tips/




