# Enumeration_WithFoothold

**This part contains the manual enumeration commands when we DO have a initial foothold into any of our target hosts.**

 ### Windows User

 * Display your login name
   ```
   whoami
   ```
 * Display user account information
   ```
   net user student
   ```
 ### Linux User
 * Basic Linux command used to confirm the identity of a specified Linux user
   ```
   id
   ```
 * Plain text file containing list of system's accounts & sometimes encrypted password
   ```
   cat /etc/passwd 
   ```
 * Name given to a computer and attachment to the network
   ```
   hostname
   ```
### Operating System Version and Architecture
 * Windows
   ```
   systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"
   ```
 * Linux
   ```
   cat /etc/issue
   cat /etc/*-release
   uname -a
   ```
### Running processes & services 
 * Windows
   ```
   tasklist /SVC
   ```
 * Linux
   ```
   ps axu
   ```
### Network info
 * Windows
   ```
   ipconfig /all
   route print
   netstat –ano 
   ```
 * Linux
   ```
   ip a 
   /sbin/route 
   ss –anp  
   ```
### Search for all SUID/SGID files (Linux)
 * Enumerate all binaries having SUID permission
   ```
   find / -perm -u=s -type f 2>/dev/null
   ```
### Firewall status & rules
 * Windows
   ```
   netsh advfirewall show currentprofile
   netsh advfirewall firewall show rule name=all
   ```
 * Linux
   ```
   etc/iptables
   ```
### Scheduled tasks
 * Windows
   ```
   schtasks /query /fo LIST /v
   ```
 * Linux
   ```
   ls -lah /etc/cron*
   cat /etc/crontab
   ```
### Installed apps & patch levels
 * Windows
   ```
   wmic product get name, version, vendor
   wmic qfe get Caption, Description, HotFixID, InstalledOn
   ```
 * Linux
   ```
   dpkg –l
   ```
