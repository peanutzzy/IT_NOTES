## DEFAULT CONFIGURATION
Default config file at */etc/postfix/main.cf*
![[Pasted image 20241019174243.png]]

## COMMANDS
![[Pasted image 20241019174355.png]]

To enumerate users use *VRFY* command. A status code of 252 will be displayed if user exists.
## DANGEROUS CONFIGURATION
![[Pasted image 20241019174605.png]]

## CONNECTION TO SMTP
Use *telnet \<ip-address\> \<port\>* for connecting to the SMTP server

## FOOTPRINTNG
Common ports: 25, 465

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

Use *--script smtp-open-relay* to identify the target SMTP server as an open relay

Use *smtp-enum-users* to bruteforce existing users on the SMTP server.