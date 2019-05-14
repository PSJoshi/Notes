## Detecting compromised linux server - some commands

### Verify md5 checksum of RPM files

```
# rpm -qa | xargs rpm -V
```

### Track network connections
```
# netstat -an
# netstat -nalp
# nestat -plant
# ss -a -e -i
```

### Watch traffic in detail on demand for a specific port
```
# tcpdump src port 6697
```

### Process tree
```
# ps -auxwf
```

### Deleted binaries still running
```
# ls -alR /proc/*/exe 2> /dev/null | grep -i deleted
```

### Process command name/cmdline
```
# strings /proc/<PID>/comm
# strings /proc/<PID>/cmdline
```

### Real process path
```
# ls -la /proc/<PID>/exe
```
### Process environment
```
# strings /proc/<PID>/environ
```
### Process working directory
```
# ls -alR /proc/*/cwd
```
### Processes running from tmp, dev directories
```
# ls -alR /proc/*/cwd 2> /dev/nulll | grep tmp
# ls -alR /proc/*/cwd 2> /dev/nulll | grep dev
```
### List all hidden directories
```
# find / -type d -name ".*"
```

### Check for zero size logs
```
# ls -al /var/log/*
```
### Dump audit logs
```
# utmpdump /var/log/wtmp
# utmpdump /var/run/utmp
# utmpdump /var/log/btmp
```
### Track last logins
```
# last
# lastb
```
### Find logs with binary content
```
# grep [[:cntrl:]] /var/log/*.log
```
### Check scheduled tasks
```
# crontab -l
# atq
# systemctl list-timers --all
```
### Look for UID-0 and GID-0
```
# grep ":0:" /etc/passwd
```
### Check sudoers file
```
# cat /etc/sudoers
# cat /etc/group
```
### Find all ssh authorized_keys files
```
# find / -name authorized_keys
```
### history file for user
```
# find / -name *history
```
### History files linked to /dev/null
```
# ls -laR / 2> /dev/null | grep *history | grep null
```
### Find all hidden directories
```
# find / -type d -name ".*"
```
### Find files modified within last day
```
# find / -mtime -1
```
### Files/directories with no user/group name
```
# find / \( -nouser -o -nogroup \) -exec ls -lg {} \;
```
### Immutable files and directories
```
# lsattr / -R 2> /dev/null | grep "\----i"
```
### Find SUID/SGID files
```
# find / -type f \( -perm -04000 -o -perm -02000 \) -exec ls -lg {} \;
```
### Find all executable files
```
# find / -type f -exec file -p '{}' \; | grep ELF
```
### Find all executable files in tmp directory
```
# find /tmp -type f -exec file -p '{}' \; | grep ELF
```
Thanks to Sandrfly security - https://www.sandflysecurity.com/wp-content/uploads/2018/11/Linux.Compromise.Detection.Command.Cheatsheet.pdf
