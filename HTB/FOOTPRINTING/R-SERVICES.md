
## CONNECTION
Use *rlogin \<ip-address\> -l \<username\>*


## FOOTPRINTNG
Common ports:  512, 513, 514

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

**R-COMMANDS**
- *rcp (remote copy)*
- *rexec (remote execution)*
- *rlogin (remote login)*
- *rsh (remote shell)*
- *rstat*
- *ruptime*
- *rwho (remote who)*
![[Pasted image 20241019200620.png]]

The */etc/hosts.equiv* contains a list of trusted host who can access the system without further authentication
![[Pasted image 20241019200729.png]]

Equivalent to *hosts.equiv* file where *.rhosts* provides a per-user configuration
![[Pasted image 20241019200840.png]]
\+ means allows any user or ip

**LISTING AUTHENTICATED USERS**
Using *rwho*
![[Pasted image 20241019201213.png]]

Using *rusers*
Ex.
*rusers -al \<ip-address\>*
![[Pasted image 20241019201248.png]]