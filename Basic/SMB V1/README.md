# SMB Vulnerability 
## Remediation

### Windows 
Using Powershell as Administrator
The computer will restart after you run the PowerShell commands to disable or enable SMBv1.
* Detect
 * Get-WindowsOptionalFeature -Online -FeatureName SMB1Protocol
* Disable
 * Disable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol
* Enable
 * Enable-WindowsOptionalFeature -Online -FeatureName SMB1Protocol
### Linux
* 

### Resources 
* https://techcommunity.microsoft.com/t5/storage-at-microsoft/stop-using-smb1/ba-p/425858 

# Validation & Testing 
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
