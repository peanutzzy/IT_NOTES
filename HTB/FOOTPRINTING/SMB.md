## DEFAULT CONFIGURATION
*cat /etc/samba/smb.conf | grep -v "#\\|\\;"*
![[Pasted image 20241017115844.png]]
![[Pasted image 20241017120327.png]]

## DANGEROUS CONFIGURATION
![[Pasted image 20241017120618.png]]

## CONNECTION TO SMB SERVER
To enumerate list of shares use: *smbclient -N -L //\<ip-address\>*
- *-N*: Null session or anonymous access without username and password
- *-L*: Lists the server's shares
- *\<ip-address\>*: The ip address of the server

Once we get ahold a name of a share we can connect to it with: *smbclient //\<ip-address\>/\<share-name\>*
NOTE: Use "anonymous" or blank as the password

Once connected to the SMB server you can use "help" to get a list of possible commands. The common commands are:
- *ls*: List files and folders in a directory
- *get*: Downloads a file or folder from the SMB server
- *put*: Uploads a file or folder to the SMB server
- *!\<cmd\>*: Executes local system commands
- *smbstatus*: Retrieves the users and relevant information that connected to the SMB server

## FOOTPRINTING
Common ports: 137,138,139, 445
### ENUMERATION
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

[**SMBmap**](https://github.com/byt3bl33d3r/CrackMapExec)
Usage:
	*smbmap -H \<ip-address\>*

[**CrackMapExec**](https://github.com/byt3bl33d3r/CrackMapExec)
Usage:
	*crackmapexec smb \<ip-address\> --shares -u \<username(blank=anonymous)\> -p \<password(blank=anonymous)\>*

[Enum4Linux-ng](https://github.com/cddmp/enum4linux-ng)
Usage:
	*python enum4linux-ng.py \<ip-address\> -A*


**RPCCLIENT**
Connect with *rpcclient -U "" \<ip-address\>*

**RPCCLIENT REQUEST COMMANDS**
- *srvinfo*: Server information
- *enumdomains*: Enumerate all domains that are deployed in the network
- *querydominfo*: Provides domain, server, and user information of deployed domains
- *netshareenumall*: Enumerates all available shares
- *netsharegetinfo \<share\>*: Provides information about a specific share
- *enumdomusers*: Enumerates all domain users
- *queryuser \<RID\>*: Provides information about a specific user
- *querygroup \<RID\>*: Provides information about a specific group

### BRUTE-FORCING USER RIDs
[Samrdump.py](https://github.com/SecureAuthCorp/impacket/blob/master/examples/samrdump.py)
Usage:
	*python samrdump.py \<ip-address\>*

