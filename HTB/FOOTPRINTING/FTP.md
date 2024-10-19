## DEFAULT CONFIGURATION
Configuration file at */etc/vsftpd.conf*
![[Pasted image 20241017062324.png]]
![[Pasted image 20241017063051.png]]

## DANGEROUS CONFIGURATION OF FTP
![[Pasted image 20241017062540.png]]

## FTP USERS
Users with denied access to FTP
*cat /etc/ftpusers*

## ANONYMOUS LOGIN TO FTP
*ftp \<ip address\>*

Once connected to the FTP server you can use the following commands:

- status: Displays the overview of the server's settings
- debug: Checks if debugging is enabled on the server
- ls: prints the files and folders on the current directory
	- You can use the -R flag to list all files inside a folder of the directory
- get \<file-name\>: Download files from the FTP server
- put \<file-name\>: Upload files from the client to the FTP server
- exit: Ends FTP server session

## DOWNLOADING FILES WITH WGET
*wget -m --no-passive \ftp://anonymous:anonymous@<ip-address\>*

## FOOTPRINTNG
Common ports: 21, 20
- NMAP - Most used tool for footprinting
	- [NSE(Nmap Scripting Engine)](https://nmap.org/book/nse.html) - A set of different scripts written for specific services

**NMAP COMMAND FLAGS**
- *--script-updatedb*: Updates the script database of NMAP
- *--script-trace*: trace the progress of NSE scripts at the network level
- *-sV*: Version scan
- *-A*: Aggressive scan
- *-sC*: Default script scan
- *-p \<port\>*:  defines which port to scan

**TLS/SSL ENCRYPTED FTP SERVER**
To access this type of FTP server, we can use *openssl* to communicate with the FTP server.
Ex. $*openssl s_client -connect \<ip-address\> -starttls ftp*
