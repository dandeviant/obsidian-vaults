Wordlists are in the same directory as [[Gobuster Directory Scanning]]'s wordlists
```bash
/usr/share/wordlists
```

Mainly for easy CTFs in TryHackMe, we will use ```rockyou.txt``` wordlist, stored and compressed in ```rockyou.txt.gz```

Extract with gunzip
>```bash
>$ gunzip rockyou.txt.gz
>```

Cracking password of a SSH private key
```bash
cp /usr/share/john/ssh2john.py /home/kali/Downloads
python3 ssh2john.py idrsa.id_rsa > output_hash
john --wordlist=/usr/share/wordlists/rockyou.txt output_hash
```