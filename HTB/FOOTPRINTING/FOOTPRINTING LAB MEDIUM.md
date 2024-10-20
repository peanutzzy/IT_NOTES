![[Pasted image 20241019224938.png]]
NMAP SCAN RESULTS

We know it uses SMB, NFS, WMI, RDP, WINRM. The client also made an account with username HTB

First lets try enumerating NFS:
- Available share: /TechSupport
- Can mount /TechSupport
- Permission denied when changing directory to /TechSupport mount

Lets then try enumerating SMB:
- Access Denied when listing shares with null session
- Tried SMBMAP - didn't work
- Tried crackmapexec - didn't work
	- Note: Pipe Line error when using HTB as username
- I forgot that it uses both port 139 and 445. Let's try again
- port 139 doesn't seem to work but let's see later

Since remote access to the server requires username and password we aren't able yet to enumerate WMI, RDP, WINRM.

Let's try enumerating NFS again since it showed an open share:
- I used the mount command incorrectly thats why I cant access it
	- used *sudo mount -t nfs 10.129.199.126:/ ts -o nolock* and it worked
	
![[Pasted image 20241019232007.png]]

I got stuck on NFS since i didn't study well the root_squash config but basically just use escalated privileges to access the folder.

Now let's begin

We got access to the folder and a file with content:
![[Pasted image 20241019235044.png]]

It shows username "alex" and password "lol123!mD"

Since smtp is disabled from the server we can assume that these credentials can be used for remote access.

lol123!mD

87N1ns@slls83

We got access to the server using xfreerdp and the credentials of alex.

Found a folder called "devapps" with a text file called "Important"

It contained "sa:87N1ns@slls83" which I suppose to be the credentials for the MSSQL server

It wasn't the credentials.

I tried using "Administrator" as username since it existed as a user on the server.

It didn't work also.

I exited the RDP.

I started it again with the username "Administrator" and the password "87N1ns@slls83"

IT WORKED!!

I went to the MSSQL application and connected using Windows Authentication and I got in.

I saw a database named "accounts" with a table called "dbo.devapps"

I queried "SELECT password FROM dbo.devapps WHERE username='HTB' "

BOOM I got to password!

It was "lnch7ehrdn43i7AoqVPK4zWR"