## CONNECTION
You can use *xfreerdp*, *rdesktop*, or *Remmina* on Linux

xfreerdp
Ex.
*xfreerdp /u:\<username\> /p:\<password\> /v:\<ip-address\>*
## FOOTPRINTNG
Common port: 3389

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

Use *--script rdp\** to use all scripts with rdp

Use *--packet-trace* to track the individual packets

WARNING: threat hunters can identify nmap if the RDP cookie *mstshash* is equal to "nmap"

**rdp-sec-check.pl**
Developed by Cisco CX Security Labs that can unauthentically determine the security settings  of RDP servers

Installation
- *sudo cpan*
- *git clone https://github.com/CiscoCXSecurity/rdp-sec-check.git && cd rdp-sec-check*
- *./rdp-sec-check.pl \<ip-address\>*


