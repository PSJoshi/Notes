## Web logs analysis - Some indicators of compromise(IOC)

### IP-level statistics:
High frequency, periodicity or volume by a single IP address or subnet is suspicious.

### User string abbrevations:
Self referencing paths(/./) or backreferences(/../) are used in path traversal attacks

### Decoded URLs and HTML entities, escapaed characters, null byte string termination
These are used by simplae signature/rule engines to avoid detection

### Unusal refererr patterns:
Page accesses with abnormal referrer url are often a signal of an unwelcome access to http endpoint

### Sequence of accesses to endpoints:
Out-of-order access to http endpoints that do not correspond to website logical flow is indicative of fuzzing or malicious explorations. e.g. if typically user access the website after logging in (/login using POST) followed by three successive GETs to /a, /b, /c. But a particular IP is repeatedly making GET requests to /b and /c without corresponding login or /a request. This could be a sign of bot automation or manual reconnaissance activity.

### User agent patterns
Perform user agent frequency analysis on user agents to alert on un-usual user agent string or extremely old client.

Web logs provide enough information about different OWASP Top Ten web application attacks.

Good Book - Machine Learning and Security: Protecting Systems with Data and Algorithms - David freeman O'reilly
 
