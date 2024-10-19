## DEFAULT MSSQL DATABASES
![[Pasted image 20241019181746.png]]
## DEFAULT CONFIGURATION
![[Pasted image 20241019181652.png]]
## DANGEROUS CONFIGURATION
![[Pasted image 20241019181717.png]]

## FOOTPRINTNG
Common port: 1443

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

There are a lot of NSE scripts you can use for MSSQL like:
- *ms-sql-info*
- *ms-sql-empty-password*
- *ms-sql-xp-cmdshell*
- *ms-sql-config*
- *ms-sql-ntlm-info*
- *ms-sql-tables*
- *ms-sql-hasdbaccess*
- *ms-sql-dac*
- *ms-sql-dump-hashes*

The script args are:
- *mssql.instance-port=\<port(default 1433)\>*
- *mssql.username=\<username(default sa)\>*
- *mssql.password=\<password(default none)\>*
- *mssql.instance-name=\<instance-name(default MSSQLSERVER)\>*

**mssqlclient.py**
Ex.
*python mssqlclient.py \<username\>:\<password\>@\<ip-address\>* -windows-auth
