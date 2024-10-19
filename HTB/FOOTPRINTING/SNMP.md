## DEFAULT CONFIGURATION
Config file at */etc/snmp/snmpd.conf*
![[Pasted image 20241019180030.png]]
## DANGEROUS CONFIGURATION
![[Pasted image 20241019180050.png]]

## FOOTPRINTNG
Common ports: 161, 162

Use tools like *snmpwalk*, *onesixtyone*, and *braa*
Ex.
*snmpwalk -v2c -c \<community-string\> \<ip-address\>*
- Enumerates all OID from a specific community string. The most common community string is *public*.

*onesixtyone -c \<comm-string-wordlist\> \<ip-address\>*
- Brute-forces available community strings using a wordlist.

*braa \<community-string\>@\<ip-address\>:.1.3.6.\**
- Brute-force individual OIDs with the *.1.3.6\**
