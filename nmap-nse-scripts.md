### How to install latest nmap scripts
I often forget the process to install latest nmap scripts from official Nmap repository. So, here is a quick note for myself!
#### Find location of nmap scripts directory
Under Windows
```
Windows Key + F, *.nse
```
Under linux
```
$ sudo find / -name '*.nse'
```
```
$ sudo locate *.nse
```
Most common place for nse script is
```
c:\Program Files\Nmap\Scripts
/usr/share/nmap/scripts
/usr/local/share/nmap/scripts
```
#### Download nse scripts from official nmap site
Nmap ```.nse``` scripts are located under https://svn.nmap.org/nmap/scripts/ repository.

It's official Git-based mirror is here - https://github.com/nmap/nmap/tree/master/scripts

So, Download the repository using git pull command.

Extract scripts folder and copy/overwrite over existing ```scripts``` directory.

#### Update scripts database (optional)
If you have internet connection, you can use Nmap script's update command
```
$ nmap –script-updatedb
```

Now, you are ready to run nmap with the latest version of NSE script and this is particularly useful for finding vulnerabilities.

Cheers!
