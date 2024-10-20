## CONNECTION
You can use *Test-WsMan* for windows and *evil-winrm* for Linux

**Test-WSMan**
Ex.
*Test-WSMan -ComputerName "\<ip-address\>" -Authentication \<auth-type\>*

**evil-winrm**
Ex. 
*evil-winrm -i \<ip-address\> -u \<username\> -p \<password\>*


## FOOTPRINTNG
Common ports: 5985, 5986

**NMAP**
Most used tool for footprinting
- [NSE(Nmap Scripting Engine)](https://nmap.org/book/nse.html) - A set of different scripts written for specific services

**NMAP COMMAND FLAGS**
- *--script-updatedb*: Updates the script database of NMAP
- *--script-trace*: trace the progress of NSE scripts at the network level
- *-sV*: Version scan
- *-A*: Aggressive scan
- *-sC*: Default script scan
- *-p \<port\>*:  defines which port to scan

Use *--disable-arp-ping* to disable arp pinging and *-n* to disable DNS resolutions

