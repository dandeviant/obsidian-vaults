## What is Searchsploit?

Source: VOD - TryHackMe! Steel Mountain with Metasploit
https://www.youtube.com/watch?v=GYm8LNn-524

---

Searchsploit is a terminal utility to look through ExploitDB (Exploit Database) only through the command line without needing to go to the website

Command
```bash
>searchsploit "<Exploit name>"
```

Sample Command:

>```bash
>$ searchsploit "Rejetto HTTP File Server"
>``` 

![[searchsploit list.png]]

Examine the given path:

Command
```bash
>searchsploit -x "<path>"
```

Sample Command (based on the output given above):

>```bash
>$ searchsploit "windows/remote/34668.txt"
>``` 

![[searchsploit info.png]]