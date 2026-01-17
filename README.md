# NetSpray  
NetSpray is a wrapper script designed to save time when performing password or hash spraying across multiple protocols. It leverages the power of [NetExec](https://www.netexec.wiki/) to automate the process efficiently.

## Installation
### Clone it
```bash
git clone https://github.com/0xmrsecurity/NetExec-Stuff.git
cd NetExec-Stuff
```
### Move
```bash
sudo mv NetSpray /usr/local/bin
sudo chmod +x /usr/local/bin/NetSpray
```
### Help Menu !
```bash
└─# NetSpray -h                                                                                             
Usage: /usr/local/bin/NetSpray <protocols|all> <targets> -u <username> [-p <password> | -H <hash>] [OPTIONS]

Required:
  protocols          Protocols to test: smb,ldap,winrm,rdp,mssql,ssh or 'all'
  targets            IP address, IP range, or file with targets (one per line)
  -u USERNAME        Username to spray

Authentication (choose one):
  -p PASSWORD        Single password to spray
  -H HASH            NTLM hash for pass-the-hash

Optional:
  --continue-on-success    Keep spraying after finding valid creds
  --no-bruteforce          Avoid bruteforce mode (safer, slower)

Examples:
  NetSpray smb 10.10.10.10 -u admin -p P@ssword123!
  NetSpray all targets.txt -u admin -p P@ssword123!
  NetSpray smb,winrm 192.168.1.10 -u admin -H aad3b435b51404ee:8846f7eaeexxxxx7ad06bdd830b7586c
```
## Usage
```bash
# All Protocals
NetSpray all target -u 'admin' -p 'p@ssword123!'

# Specific Protocals
NetSpray smb,winrm,rdp,ldap,ssh,mssql target -u '' -p ''

# Available Protocals
smb
ldap
winrm
ssh
mssql
```
