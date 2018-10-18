### Various log file under /var/log

* alternatives.log -- "run with" suggestions from update-alternatives
* apport.log -- information on intercepted crashes
* auth.log -- user logins and authentication mechanisms used
* boot.log -- boot time messages
* btmp -- failed login attempts
* dpkg.log -- information on when packages were installed or removed
* lastlog -- recent logins (use the lastlog command to view
* faillog -- information on failed login attempts -- all zeroes if none have transpired (use faillog command to view)
* kern.log -- kernel log messages
* mail.err -- information on errors detected by the mail server
* mail.log -- information from mail server
* syslog -- system services log
* wtmp -- login records


### Journalctl
In addition to log files(/var/log), you should also watch journalctl activities. The journal represents an important collection of information on user and kernel activity and this information is retrieved from a variety of sources on the system.

Some useful commands that you should run:
```
Returns total no of lines
$ journalctl | wc -l

```
Journal logs from a date
$ journalctl --since "2018-10-06 10:00"
```
```
Log entries for a particular device
$ journalctl -u networking.service
```
```
Disk usage
$ journalctl --disk-usage
```
```
Activity for a specific process
$ journalctl _PID=780
```

