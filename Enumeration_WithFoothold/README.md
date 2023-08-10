# Enumeration_NoFoothold

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
### Operating System Version and Architecture - Windows
 * 
   ```
   systeminfo | findstr /B /C:"OS Name" /C:"OS Version" /C:"System Type"
   ```
### Operating System Version and Architecture - Linux
 * 
   ```
   cat /etc/issue
   cat /etc/*-release
   uname -a
   ```
### Running processes & services - Windows
 * 
   ```
   tasklist /SVC
   ```
### Running processes & services - Linux
 * 
   ```
   ps axu
   ```
### Network info - Windows
 * 
   ```
   ipconfig /all
   route print
   netstat –ano 
   ```
### Network info - Linux
 * 
   ```
   ip a 
   /sbin/route 
   ss –anp  
   ```
### Search for all SUID/SGID files - Linux
 * Enumerate all binaries having SUID permission
   ```
   find / -perm -u=s -type f 2>/dev/null
   ```
