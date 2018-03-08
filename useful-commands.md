# Useful commands
### OS statistics
```
$ ifconfig -a
$ netstat -s
$ netstat -ni
$ vmstat -S m 1
```
### NIC configuration Ethtool
Format:
Show            ;           Set 
```
$ ethtool -S eth0 // Statistics
$ ethtool -S eth0 | egrep '(rx_missed|no_buffer)'    // Drop Values  
$ ethtool -g eth0 ; ethtool -G eth0 rx 4096 tx 4096 // FIFO RX Descriptors
$ ethtool -k eth0 ; ethtool -K gro on gso on rx on // Offloading
$ ethtool -a eth0 ; ethtool -A rx off autoneg off // Pause Frames
$ ethtool -c eth0 ; ethtool -C eth0 rx-usecs 100 // Interrupt Coalescence 
```
### PCAP statistical data
```
$ capinfos file.pcap
$ tcpslice -r file.pcap
$ tcpdstat file.pcap
$ tcpprof -S lipn -P 30000 -r file.pcap
```
### Number System Conversions
```
$ printf "%d" 0x2d
$ printf "%x" 45
$ printf '\x47\x45\x54\x0a'
$ echo "GET" | hexdump -c 
$ echo "GET" | hexdump -C 
```
### Session & Flow Data
```
$ iftop -i eth0.pcap // live only, replay for same effect
```
// use -i instead of -r for interface
```
$ tcpflow -c -e -r file.pcap 'tcp and port (80 or 443)'
$ tcpflow -r file.pcap tcp and port \(80 or 443\)
$ tcpick -r file.pcap -C -yP -h 'port (25 or 587)'
```
// [-wRu] write both flows; [-wRC] write client flows only ; [-wRS] write server flows only
```
$ tcpick -r file.pcap -wRu 
```

### Replay
```
$ tcpreplay -M10 -i eth0 file.pcap
$ netsniff-ng --in file.pcap --out eth0
$ netsniff-ng --in eth0.pcap --out eth1.pcap
$ trafgen --dev eth0 --conf trafgen.txf --bind-cpu 0
```
### Audit Record Generation And Utilization System
```
$ argus -r file.pcap -w file.argus
$ ra -nnr file.argus ; ra -Z b -nnr file.argus
$ ra -nnr file.argus - host 192.168.1.1 and port 80
$ racluster -M rmon -m saddr -r file.argus
$ ra -nnr file.argus -w - - port 22 | racluster -M rmon -m saddr -r - | rasort -m bytes -r -
$ racluster -M rmon -m proto -r file.argus -w - | rasort -m pkts -r - 
$ racluster -M rmon -m proto sport -r file.argus
$ ragraph bytes -M 30s -r file.argus -w bytes.png
$ ragraph pkts -M 30s -r file.argus -w pkts.png
$ ra -nnr file2.argus -s saddr,daddr,loss | sort -nr -k 3 | head -20
$ ragraph dbytes sbytes -M 30s -r file.argus - dst port 80 and dst port 443
$ ragraph dbytes sbytes dport sport -fill -M 30s -r file.argus
```
### Network Forensics - File Extraction
```
$ tcpdump -nni eth0 -w image.pcap port 80 &
$ wget http://upload.wikimedia.org/wikipedia/en/5/55/Bsd_daemon.jpg
$ jobs
$ kill %1
$ tcpflow -r image.pcap
$ tcpxtract -f file.pcap -o xtract/
```

### change MAC's
```
$ tcprewrite --enet-dmac=00:44:66:FC:29:AF,00:55:22:AF:C6:37
--enet-smac=00:66:AA:D1:32:C2,00:22:55:AC:DE:AC --infile=in.pcap
--outfile=out.pcap
```
# randomize IP's
```
$ tcprewrite --seed=423 --infile=in.pcap --outfile=out.pcap
```
Ref - http://www.draconyx.net/talks/pcapworksheet.txt and many thanks to John Schipp.

