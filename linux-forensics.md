### Collecting volatile data
* Date and time
* network interfaces
* promiscuous mode
* network connections
* open ports (TCP as well as UDP), Listening ports/services
* running processes and their ports
* open files
* routing tables
* mounted filesystem(s)
* loaded kernel modules
* kernel version
* uptime
* last reboot time
* filesystem datetime stamps
* hash values of system files
* current logged in users
* current users with noshell, current users with active shell
* login history, login times
* user accounts, inactive accounts
* user history files
* hidden files and directories
* suid/sgid files
### Dumping RAM
* using fmem kernel module
* using lime
* using /proc/kcore
### Acquiring filesystem images
* using dd
* using dcfldd
* write blocking options
  * using forensics linux distributions like SIFT, Kali
  * udev rule based blocker for devices like USB
* Analysis of strange file
  * regular files in /dev
  * user history files
  * hidden files
  * suid/sgid files
  * too old date files
  * finding deleted files in last 7 days/last month
### Timeline analysis
* use of autospy to establish timeline
* when was the system installed, rebooted, upgraded etc
* changed files
* newly created files
### Netwokr forensics
* usage of snort for detection of malicious packets
* bro for detailed logs analysis of http/dns/https/ traffic
* using tcpstat
* conversation analysis using tcpflow
### Writing reports
* autospy
* dradis
* openoffice/MS-office
### File forensics
* comparing file hash to known values
* unknown file analysis using
  * file command
  * strings command
  * viewing symbols using nm
  * reading objects using objdump
  * analysis using gdb
