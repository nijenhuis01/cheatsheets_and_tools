## gobuster cheatsheets

|Command|Description|
|---|---|
|gobuster dir -u http://10.10.10.121/ -w /usr/share/dirb/wordlists/common.txt|Run a directory scan on a website|
|gobuster dns -d inlanefreight.com -w /usr/share/SecLists/Discovery/DNS/namelist.txt|Run a sub-domain scan on a website|