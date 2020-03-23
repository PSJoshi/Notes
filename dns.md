### Recursive vs Non-Recursive(Iterative) DNS query

* Iterative DNS queries are the one in which DNS server is queried and returns an answer without querying other DNS servers. Iterative queries are non-recursive queries.

* Recursive queries occur when DNS client requests information from DNS server that is set to query subsequent DNS servers until a definitive answer is returned to client. The queries made to subsequent DNS servers from the first DNS server are iterative queries. It may be noted that root server's are always iterative servers.

A DNS server that supports recursive resolution is vulnerable to DOS (denial of service) attacks, DNS cache poisoning, unauthorized use of resources, and root name server performance degradation.

#### Ref:
* https://www.slashroot.in/difference-between-iterative-and-recursive-dns-query

### Some flags in DNS packet

#### AA - Authoritative answer 
specifies if the responding name server is the authority for domain name in question
* 0 - non-authoritative
* 1 - authoritative

#### TC - Truncated
Indicates that only first 512 bytes of reply was returned
* 0 - truncated
* 1 - message truncated

#### RD - Recursion desired
Name server is directed to pursue query recursively
* 0 - recursion not desired
* 1 - recursion desired

#### RA - Recursion available
Indicates if recursive query support is available on name server
* 0 - recursive query support not available
* 1 - recursive query support available

#### Z 
This flag is reserved for future use

## Tracking evil in DNS logs
DNS logs ( either from PassiveDNS or Bro/Zeek logs) contain lot of useful information and it can be used to track down malware. Please find below some of the queries that you can use to extract malicious domains.

### Multiple level subdomains
DNS queries usually do not use multiple subdomains. High number of subdomains might indicate
that DNS is malicious. However, Content Delivery Networks (CDN) can be exception to this type 
of queries.
```
$ echo W.0228452040.I0.aHR0cHM6Ly9zc2wuZ3N0YXRpYy5jb20v.19.x.wpad.software | tr -cd '.' | wc -c
```
If the number of dots are more than 5, it's safe to assume that something is not alright!!

### Domain length / DNS query length 
Total length of dns query is a good indicator of malicious communication as long queries are often used for data exfiltration or communication with C&C servers. The longer the length of request query, the risk that it might be malicious is larger.

```
$ echo -n W.0228452040.I0.aHR0cHM6Ly9zc2wuZ3N0YXRpYy5jb20v.19.x.wpad.software | wc 
``` 
The rule of thumb you can take is:
if you find 63 characters in any part (subdomain) then the request is likely malicious.

### Domain Entropy
It is seen that entropy of malicious domains is higher than entropy of legitimate domains.
```
$ echo -n W.0228452040.I0.aHR0cHM6Ly9zc2wuZ3N0YXRpYy5jb20v.19.x.wpad.software | ent
```
Average entropy of top 11k Alexia domains is around 3.1
However, relying on entropy alone can result in a lot number of false positive as entropy of CDN networks is also higher. So, you need to combine this indicator with other one like domain query length and it can be very effective.

### Mix of uppercase and lowercase letters
If there are mixed upper/lower case characters in domains, it should be investigated as it might be base64 encoded data.
Usually, most of the domain characters are either in lowercase or uppercase.
```
$ echo W.0228452040.I0.aHR0cHM6Ly9zc2wuZ3N0YXRpYy5jb20v.19.x.wpad.software | tr -cd '[A-Z]' | wc -c
13
$ echo W.0228452040.I0.aHR0cHM6Ly9zc2wuZ3N0YXRpYy5jb20v.19.x.wpad.software | tr -cd '[a-z]' | wc -c
25
```

### Non-alphanumeric DNS requests
Domain name registration is allowed only with alphabet letters, digits and hypens. Domains which are using other characters like Punycode are rare.
Non-alphanumeric DNS requests are very rare and in most cases, these are related to malicious behaviour.

```
$ host cmVkdGVhbS5wbA==.redteam.pl
cmVkdGVhbS5wbA==.redteam.pl is an alias for redteam.pl.
```
### Use of Punycode
Punycode (RFC 3492) allows usage of special letters from alphabets other than english e.g. polish in domain names
Punycode is not very popular and is often used in Phishing or malware campigns. So, it is a good practice to keep track of
puny domains.

### Types of dns requests 
Common DNS queries are of Type - A, AAAA, and PTR. If you encounter unusual queries like AXFR, ANY, TXT, these need a closer look for investigation.

### TTL (time to live)
A lower TTL value indicates the probability of malicious behaviour. But, it's not true in case of CDNs such as Cloudflare where TTL is 300 seconds.
If you observe a TTL of 0-1 seconds, then it's likely a malicious domain.

#### Ref:
The following article cover a lot of DNS queries that indicate possible malicious DNS communication and it is highly recommended to go through it for more information - https://blog.redteam.pl/2019/08/threat-hunting-dns-firewall.html



