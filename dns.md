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
Reserved for future use
