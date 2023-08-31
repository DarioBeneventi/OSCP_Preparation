# Enumeration_By_Port_Number

**This part contains manual enumeration methods for specific port numbers that we encounter on a Pentest, be aware that automated tools are not allowed on the OSCP exam**

 ### PORT 21 - FTP

 * Anonymous login 
   ```
   ftp 10.10.1.8 
   name >> anonymous
   ```
 * Look for version specific exploit
   ```
   Nc 10.10.4.226 21 (can give us info on what service & version ftp is running)
   searchsploit ftpversion
   ```
 ### PORT 22 - SSH
 * Grab a banner & version 
   ```
   nc -nv 10.10.1.8 22
   ```
 * Nmap script ssl-heartbleed (care makes noise)
   ```
   nmap -p 22 --script ssl-heartbleed 10.10.1.8
   ```
### PORT 25 - SMTP
 * Check for existance of email
   ```
   VRFY
   ```
 * Membership mailing list
   ```
   EXPN
   ```
### PORT 53 - DNS
 * Standard DNS Query
   ```
   nslookup targetdomain.com  
   ```
 * Mail Exchanger DNS Query
   ```
   dig targetdomain MX
   ```
 * Name Server DNS Query
   ```
   dig targetdomain NS
   ```
 * DNS Zone Transfer Query
   ```
   dig axfr @10.10.1.8 targetdomain
   dnsrecon -d targetdomain ​-a --name_server target​server
   ```
 * Bruteforcing subdomain enumeration (care for noise)
   ```
   dnsmap targetdomain
   ```
