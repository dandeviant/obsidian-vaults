# Nmap basics

Home: [[(Main) Tools You Can Learn]]

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

