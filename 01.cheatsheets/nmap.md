## Nmap cheatsheet

### Find hosts
```
sudo nmap 10.129.2.0/24 -sn -oA tnet | grep for | cut -d" " -f5
```
### Find Hosts with NMAP
|Nmap options|Description|
|---|---|
|-sn| Disables port scan|
|-PR|Arp scan|
|-PU|UDP ping scan|
|-PE|Echo ping scan|
|-PP|ICMP Ping scan|
|-PM|Mark ping scan|
|-PS|SYN ping scan|
|-PA|ACK ping scan|
|-PO|Different protocols scan|
|nmap -sn -PR 10.10.1.0/24||

### Scanning options
|Nmap options|Description|
|---|---|
|10.10.10.0/24|	Target network range|
|-sn|Disables port scanning|
|-Pn|Disables ICMP Echo Requests|
|-n|Disables DNS Resolution|
|-PE|Performs the ping scan by using ICMP Echo Requests against the target|
|--packet-trace|Shows all packets sent and received|
|--reason|Displays the reason for a specific result|
|--disable-arp-ping|Disables ARP Ping Requests|
|--top-ports=<num>|Scans the specified top ports that have been defined as most frequent|
|-p-|Scan all ports|
|-p22-110|Scan all ports between 22 and 110|
|-p22,25|Scans only the specified ports 22 and 25|
|-F|Scans top 100 ports|
|-sS|Performs an TCP SYN-Scan Stealth Half open |
|-sA|Performs an TCP ACK-Scan (No respons is statefull FW - RST = no FW)|
|-sX|Xmas scan (FIN, URG, PUSH)|
|-sM|Maimon scan (FIN, ACK)|
|-sT|TCP scan (Full 3 way handshake end with a RST)|
|-sU|Performs an UDP Scan (No repons = open - ICMP unreachable = port closed)|
|-sV|Scans the discovered services for their versions|
|-sC|Perform a Script Scan with scripts that are categorized as "default"|
|--script <script>|Performs a Script Scan by using the specified scripts|
|-O|Performs an OS Detection Scan to determine the OS of the target|
|-A|Performs OS Detection, Service Detection, and traceroute scans|
|-D|RND:5	Sets the number of random Decoys that will be used to scan the target|
|-e|Specifies the network interface that is used for the scan|
|-S|10.10.10.200	Specifies the source IP address for the scan|
|-g|Specifies the source port for the scan|
|--dns-server <ns>|DNS resolution is performed by using a specified name server|

### Output Options
|Nmap options|Description|
|---|---|
|-oA filename|Stores the results in all available formats starting with the name of "filename"|
|-oN filename|Stores the results in normal format with the name "filename"|
|-oG filename|Stores the results in "grepable" format with the name of "filename"|
|-oX filename|Stores the results in XML format with the name of "filename"|

### Performance options
|Nmap Options|Description|
|---|---|
|--max-retries <num>|Sets the number of retries for scans of specific ports|
|--stats-every=5s|Displays scan's status every 5 seconds|
|-v/-vv|Displays verbose output during the scan|
|--initial-rtt-timeout 50ms|Sets the specified time value as initial RTT timeout|
|--max-rtt-timeout 100ms|Sets the specified time value as maximum RTT timeout|
|--min-rate 300|Sets the number of packets that will be sent simultaneously|
|-T <0-5>|Specifies the specific timing template|

### TTL
|Operationg System|Time To Life|TCP Window Size|
|---|---|---|
|Linux|64|5840|
|FreeBSD|64|65535|
|OpenBSD|64|16384|
|Windows|128|65,535b to 1 GB|
|Cisco Routers|255|4128|
|Solaris|255|8760|
|AIX|255|16384|
