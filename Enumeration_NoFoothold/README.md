# Enumeration_NoFoothold

This part contains the manual enumeration commands when we have no initial foothold into any of our target hosts.

 ### Nmap 

 * Quick scan to find running hosts
   ```
   nmap 10.11.1.0/24 -sn 
   ```
 * Light scan on top 100 ports
   ```
   nmap 10.11.1.8 --top-ports 100 -open
   ```
 * Heavy scan on all ports, -sV stands for service detection & --reason will make Nmap include the packet type that determined the port and host state
   ```
   nmap 10.11.1.8 -p- -sV -reason
   ```
  * Heavier scan on specific ports, -v is for verbose and -A stands for agressiive
    ```
    nmap 10.11.1.8 -p 21,22,80,111 -reason -v -A 
    ```
  * UDP scan 
    ```
    sudo nmap -sUV -T4 -F --version-intensity 0 10.11.1.8
    ```
 ### NmapAutomater
 * Check all available parameters
   ```
   ./nmapAutomator.sh -h
   ```
 * Full scan of the target 
   ```
   ./nmapAutomator.sh --host 10.1.1.1 --type All
   ```
### Nikto
 * Scan a web server
   ```
   nikto -host http://10.11.1.71 -output Desktop/OSCP/Labs/71/71_niktoscan.txt 
   ```
### GoBuster
 * Enumerate a web server for known directories
   ```
   gobuster dir -u http://10.10.1.218 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt  
   ```
### SMB enumeration
 * SMB shares
   ```
   nmap -p 445 --script=smb-enum-shares.nse,smb-enum-users.nse 10.10.18.26
   Smbmap –H 10.10.70.166 
   ```
 * Inspect/connect to found SMB shares
   ```
   smbclient //10.10.18.26/sharefoundinpreviouscommand
   ```
 * Download SMB share
   ```
   smbget -R smb://10.10.44.179/sharefoundinpreviouscommand
   ```
### Netcat
 * Connect to FTP using nc - can give us info on what service & version ftp is running
   ```
   Nc 10.10.4.226 21
   ```
### NFS Share
 * Check what mounts we can see
   ```
   nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount 10.10.91.51
   ```
