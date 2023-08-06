# OSCP_Preparation


## Enumeration_NoFoothold
 ### Nmap 

 nmap 10.11.1.0/24 -sn (quick scan to find running hosts) 
 nmap 10.11.1.8 --top-ports 100 -open (Light scan on top 100 ports) 
 nmap 10.11.1.8 -p- -sV -reason (Heavy scan on all ports (-sV stands for service detection, checks what versions are running)) 
 nmap 10.11.1.8 -p 21,22,80,111 -reason -v -A (Heavier scan on specific ports) 
 sudo nmap -sUV -T4 -F --version-intensity 0 10.11.1.8 (UDP scan) 
