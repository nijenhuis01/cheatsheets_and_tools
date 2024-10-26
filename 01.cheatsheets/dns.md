## DNS

### DNS Types
|Record Type|Description|
|---|---|
|A|Maps a hostname to an IPv4 address|
|AAAA|Maps a hostname to an IPv6 address|
|CNAME|Creates an alias for a hostname, pointing it to another hostname|
|MX|Specifies mail servers responsible for handling email for the domain|
|NS|Delegates a DNS zone to a specific authoritative name server|
|TXT|Stores arbitrary text information|
|SOA|Contains administrative information about a DNS zone|

### Subdomain Brute-Forcing
|Record Type|Description|
|---|---|
|dnsenum example.com -f subdomains.txt||

### Virtual HOST
|Record Type|Description|
|---|---|
|gobuster vhost -u http://192.0.2.1 -w hostnames.txt||

