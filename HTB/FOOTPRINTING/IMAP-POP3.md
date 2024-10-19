## IMAP/POP3 COMMANDS
![[Pasted image 20241019175211.png]]

![[Pasted image 20241019175222.png]]

## DANGEROUS CONFIGURATION
![[Pasted image 20241019175243.png]]

## CONNECTION
**TLS CONNECTION TO POP3**
*openssl s_client -connect \<ip-address\>:pop3s*

**TLS CONNECTION TO IMAP**
*openssl s_client -connect \<ip-address\>:imaps*
## FOOTPRINTNG
Common ports(IMAP): 143, 993
Common ports(POP3): 110, 995

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
