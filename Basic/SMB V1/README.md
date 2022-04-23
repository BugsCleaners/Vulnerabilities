# SMB Vulnerability 
## Prerequisite
*  Kali Machine or Linux Machine 
## Basic tool:  
### Step 1 (Discover SMB Service ):
* nmap 10.1.100.58
### Step 2 (Enumerate SMB [ Share folders & OS Users ])
* 	nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.1.100.58

### step 3 (SMB client)
* 	smbclient \\10.1.100.58\\anonymous 
* 	smbclient \\\\10.1.100.58\\anonymous -U anonymous
or 
* 	smbclient \\10.1.100.58\\sharefolder -U UserTest
* provide the password 
## Advance tool: 

### Step 1
* 	./smbmap.py –H 10.1.100.58
