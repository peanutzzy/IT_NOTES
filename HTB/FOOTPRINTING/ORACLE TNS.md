## DEFAULT CONFIGURATION
![[Pasted image 20241019182534.png]]
![[Pasted image 20241019182546.png]]
PlsqlExclusionList
![[Pasted image 20241019182646.png]]

## ORACLE TOOLS SETUP
```bash
#!/bin/bash

sudo apt-get install libaio1 python3-dev alien -y
git clone https://github.com/quentinhardy/odat.git
cd odat/
git submodule init
git submodule update
wget https://download.oracle.com/otn_software/linux/instantclient/2112000/instantclient-basic-linux.x64-21.12.0.0.0dbru.zip
unzip instantclient-basic-linux.x64-21.12.0.0.0dbru.zip
wget https://download.oracle.com/otn_software/linux/instantclient/2112000/instantclient-sqlplus-linux.x64-21.12.0.0.0dbru.zip
unzip instantclient-sqlplus-linux.x64-21.12.0.0.0dbru.zip
export LD_LIBRARY_PATH=instantclient_21_12:$LD_LIBRARY_PATH
export PATH=$LD_LIBRARY_PATH:$PATH
pip3 install cx_Oracle
sudo apt-get install python3-scapy -y
sudo pip3 install colorlog termcolor passlib python-libnmap
sudo apt-get install build-essential libgmp-dev -y
pip3 install pycryptodome
```

Use *./odat.py -h* to determine if installation is successful

## COMMANDS
For commands visit https://docs.oracle.com/cd/E11882_01/server.112/e41085/sqlqraa001.htm#SQLQR985
## CONNECTION TO MSSQL
Once you obtain a username, password, and an SID of the MSSQL server, use *sqlplus \<username\>/\<password\>@\<ip-address\>/\<SID\>*

**PRIVILEGE ESCALATION**
To test if privilege escalation is possible, use  *sqlplus \<username\>/\<password\>@\<ip-address\>/\<SID\> as sysdba*
## FOOTPRINTNG
Common port: 1521

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

Use *--script oracle-sid-brute* to brute-force the SID of a database instance

**odat.py**
Ex.
*./odat.py all -s \<ip-address\>*
- Uses all the modules of odat for enumeration

File Upload
*./odat.py utlfile -s \<ip-addess\> -d \<SID\> -U \<username\> -P \<password\> --sysdba --putFile \<upload-to-folder(ex. C:\\\\inetpub\\\\wwwroot)\> \<upload-as-filename\>  \<file-to-upload\>*

Check if the uploaded file is present
*curl -X GET http:\/\/\<ip-address\>/\<filename\>*


