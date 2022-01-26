# Nmap basics

Home: [[1. (Main) Tools You Can Learn]]

Rustscan: An Alternative for Nmap
GitHub Link: https://github.com/RustScan/RustScan/releases

---

> ```bash
> nmap -h
> ```

Sample Usage of Nmap

>```bash
>sudo nmap -sC -sV -oN output 192.168.0.1
>```

The syntax of nmap
>```bash
>sudo nmap <flags> <target IP>
>```

Basic Flags for Nmap Commands

>```-sC``` = scan using default scripts
>```-sV``` = scan services and the versions
>```-oN <filename>``` = Save the output of scan in a grepable file


More flags
>- Provide a file as input for list of targets ```-iL```
> ```bash
> nmap -iL list_of_hosts.txt
> ```
> - List of hosts Nmap will scan ```-sL```
> ```bash
> nmap -sL TARGETS
> ```
> - Remove DNS server Nmapping ```-n```

---
### Summary

| Scan Type  | 	Example Command |
| --- | --- |
| ARP Scan 	| ```sudo nmap -PR -sn MACHINE_IP/24``` | 
| ICMP Echo Scan | 	```sudo nmap -PE -sn MACHINE_IP/24```| 
| ICMP Timestamp Scan | 	```sudo nmap -PP -sn MACHINE_IP/24```| 
| ICMP Address Mask Scan 	| ```sudo nmap -PM -sn MACHINE_IP/24```| 
| TCP SYN Ping Scan | 	```sudo nmap -PS22,80,443 -sn MACHINE_IP/30```| 
| TCP ACK Ping Scan | 	```sudo nmap -PA22,80,443 -sn MACHINE_IP/30```| 
| UDP Ping Scan 	| ```sudo nmap -PU53,161,162 -sn MACHINE_IP/30```| 

- Remember to add ```-sn``` if you are only interested in host discovery without port-scanning.
- Omitting ```-sn``` will let Nmap default to port-scanning the live hosts.

| Option 	| Purpose| 
| --- | --- | 
| ```-n ```	| no DNS lookup| 
|``` -R``` | 	reverse-DNS lookup for all hosts | 
| ```-sn``` | 	host discovery only| 
