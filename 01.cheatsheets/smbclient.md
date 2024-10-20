## SMBClient cheatsheet

|command|Description|
|---|---|
|smbclient -N -L \\\\10.129.42.253|List SMB Shares|
|smbclient \\\\10.129.42.253\\users|Connect to an SMB share|
|snmpwalk -v 2c -c public 10.129.42.253 1.3.6.1.2.1.1.5.0|Scan SNMP on an IP|
|onesixtyone -c dict.txt 10.129.42.254|Brute force SNMP secret string|