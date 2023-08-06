# OSCP_Preparation


## Enumeration_NoFoothold
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
  
