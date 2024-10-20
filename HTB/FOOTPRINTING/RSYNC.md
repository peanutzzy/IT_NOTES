## FOOTPRINTNG
Common port: 873

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

**PROBE ACCESSIBLE SHARES**
*nc -nv \<ip-address\> 873*

**ENUMERATING OPEN SHARE**
*rsync -av --list-only rsync:\/\/\<ip-address\>/\<share-name\>*

