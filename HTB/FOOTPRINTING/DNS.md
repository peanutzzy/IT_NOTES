## DEFAULT CONFIGURATION
Common configuration files are:
*named.conf.local*
*named.conf.options*
*named.conf.log*
Use *cat /etc/bind/named.conf.local*
![[Pasted image 20241019170239.png]]

## DANGEROUS CONFIGURATION
![[Pasted image 20241019170407.png]]
## FOOTPRINTNG

Use *dig* to get DNS records.
Ex.
Get nameserver/s of the domain using the specified DNS server
*dig ns \<domain-name\> @\<dns-server\>*
![[Pasted image 20241019170605.png]]

Get the DNS server version
*dig CH TXT version.bind 10.129.120.85*
![[Pasted image 20241019170746.png]]

Get all the records of a domain name using the specified DNS server
*dig any \<domain-name\> @\<dns-server\>*

**ZONE TRANSFER**
*NOTE: Zone transfers require a rndc-key to ensure only legitimate and trusted DNS servers synchronize unless allow-transfer is set to a subnet then anyone could query a zone transfer(you can only ZONE TRANSFER to your computer from the DNS server)*

A zone transfer refers to transferring the DNS records of all domain names to a different server. Its purpose is to allow a backup DNS server incase the main DNS server fails. It ensures all the DNS servers are synchronized. The difference between querying the domain and zone transfer is the latter retrieves all the information on a domain that is otherwise hidden on query.

Ex.
*dig axfr inlanefreight.htb @10.129.14.128*
![[Pasted image 20241019171706.png]]
