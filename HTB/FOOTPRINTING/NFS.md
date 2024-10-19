## DEFAULT CONFIGURATION
Configuration file at */etc/exports*

![[Pasted image 20241017185201.png]]
## DANGEROUS CONFIGURATION OF NFS
![[Pasted image 20241017185344.png]]
## FOOTPRINTNG
Common Ports: 111, 2049
### ENUMERATION
**NMAP**
Most used tool for footpTrinting
- [NSE(Nmap Scripting Engine)](https://nmap.org/book/nse.html) - A set of different scripts written for specific services

**NMAP COMMAND FLAGS**
- *--script-updatedb*: Updates the script database of NMAP
- *--script-trace*: trace the progress of NSE scripts at the network level
- *-sV*: Version scan
- *-A*: Aggressive scan
- *-sC*: Default script scan
- *-p \<port\>*:  defines which port to scan

**SHOW NFS SHARES**
*showmount -e \<ip-address\>*

**MOUNT NFS SHARE**
*sudo mount -t nfs \<ip-address\>:/ \<nfs-dir\> -o nolock*

**UNMOUNTING**
*sudo umount \<nfs-dir\>*




IMPORTANT NOTE: We can also use NFS for further escalation. For example, if we have access to the system via SSH and want to read files from another folder that a specific user can read, we would need to upload a shell to the NFS share that has the `SUID` of that user and then run the shell via the SSH user.
