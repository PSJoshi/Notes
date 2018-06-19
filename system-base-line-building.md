The following commands are helpful to establish a system base line.
## User Information
#### Users
```
$ cat /etc/passwd | cut -d ":" -f 1
```
#### Uid information
```
$ cat /etc/passwd | cut -d ":" -f 3
```
#### Gid information
```
$ cat /etc/passwd | cut -d ":" -f 4
```
#### Root users
```
$ grep -v -E "^#" /etc/passwd | awk -F: `$3 == 0 { print $1 }`
```
### Cron jobs
#### Own cron jobs
```
$ crontab -l -u `whoami`
```
#### Job list ( own as well as other users)
```
$ ls -la /etc/cron
$ ls -laR /etc/cron
```
#### Spool cron jobs
```
$ sudo ls -la /var/spool/cron/crontabs 
```
### System information
#### Kernel
```
$ uname -r
```
#### Hostname
```
$ uname -n
```
#### Architecture
```
$ uname -m
```
#### Shells present
```
$ cat /etc/shells | grep "bin" | cut -d "/" -f3
```
#### Environement
```
$ env
```
#### Path information
```
$ $PATH
```
### Password information
#### Umask
```
$ grep -i "^umask" /etc/login.defs
```
#### Password - max days
```
$ grep -i "^pass_max" /etc/login.defs
```
#### Password - min days
```
$ grep -i "^pass_min" /etc/login.defs
```
#### Password - warning days
```
$ grep -i "^pass_warn" /etc/login.defs
```
#### Password - encryption method
```
$ grep -i "^encryption_method" /etc/login.defs
```
