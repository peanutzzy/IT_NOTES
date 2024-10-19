## DEFAULT CONFIGURATION
Config file at */etc/mysql/mysql.conf.d/mysqld.cnf*
![[Pasted image 20241019180924.png]]
## DANGEROUS CONFIGURATION
![[Pasted image 20241019180955.png]]
Only dangerous if not assigned correctly.
## CONNECTION TO MYSQL SERVER
To connect to the MySQL server use *mysql -u \<username\> -p\<password(optional)\> -h \<ip-address\>*. Note no space between *-p* flag and the password

**COMMANDS**
![[Pasted image 20241019181452.png]]

## FOOTPRINTNG
Common port: 3306

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

Use *--script mysql* to get more detailed info

