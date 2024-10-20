## DEFAULT CONFIGURATION
Config file at */etc/ssh/sshd_config*

## DANGEROUS CONFIGURATION
![[Pasted image 20241019195507.png]]


## FOOTPRINTNG
Common port: 22

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

**SSH-AUDIT**
Download ssh-audit
*git clone https://github.com/jtesta/ssh-audit.git && cd ssh-audit*

Run
*./ssh-audit.py \<ip-address\>*

**CHANGE AUTHENTICATION METHOD**
*ssh \<username\>@\<ip-address\> -o PreferredAuthentications=password*

