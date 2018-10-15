## Threat hunting using Facebook OSQuery

### List logged in users in the system at present
```
osquery> select * from logged_in_users;
```

### Find all previous logins
```
osquery> select * from last;
```

### List Firewall rules
```
osquery> select * from iptables;
osquery> select chain, policy, src_ip, dst_ip from iptables;
```

### Find all jobs scheduled by crontab
```
osquery> select command,path from crontab;
```

### Find all files with setuid enabled.(suid bit set)
```
osquery> select * from suid_bin;
```

### Find list of kernel modules
```
osquery> select name, used_by, status from kernel_modules where status='Live';
```

### Find listening ports for any backdoors
```
osquery> select * from listening_ports;
```

### Find file activity in server along with responsible user
```
osquery> select * from file_events;
```

### Find top 10 largest processes by resident memory size
```
osquery> select pid, name, uid, resident_size from processes order by resident_size desc limit 10;
```

### Find all running processes
```
osquery> select * from processes;
```

### Find the process count and name for top 10 active processes
```
osquery> select count(pid) as total, name from processes group by name order by total desc limit 10;
```

### Find any listening ports/addresses that are not as per organization policy 
```
osquery> select distinct process.name listening.port,listening.address,process.pid from processes as process JOIN listening_ports as listening ON process.pid = listening.pid;
```
### Attackers often delete malicious binary file after running in the system. Find all such processes with no corresponding disk file ( valid file path)
```
osquery> select name,path,pid from processes where on_disk=0;
```

### Find any malware reverse shell
```
osquery> select * from processes where cmdline like 'bin/bash -i >& /dev/tcp%';
```
### Arp spoofing attack
```
osquery> select * from ( select count(1) as mac_count, mac from arp_cache group by mac) where mac_count>1;
```
### Watch a process with strict RSS limits
```
osquery> SELECT i.pid, i.version, p.resident_size, p.user_time, p.system_time, uptime.total_seconds FROM osquery_info i, processes p, uptime WHERE p.pid = i.pid;
```

#### Ref:
* OSQuery to monitor linux - https://linoxide.com/monitoring-2/setup-osquery-monitor-security-threat-ubuntu/

