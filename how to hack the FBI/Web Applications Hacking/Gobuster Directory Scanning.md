# Gobuster command

Home: [[1. (Main) Tools You Can Learn]]

-------------------------------
gobuster is basically a **HTTP web app hacking tools** to see what directory is accessible thru the server of the web app. It should be fucking easy...

```bash
	
gobuster dir -u http://$IP -w /usr/share/wordlists/<choose wordlists>

```


You can just straight up download gobuster without updating anything altho updating is a good practice when using Linux

> ```bash
> sudo apt-get install gobuster
> ```

Where to find the damn wordlists?

>```bash
>/usr/share/wordlists/dirbuster
>```

OR

>```bash
>/usr/share/wordlists/dirb
>```

- p.s. : the `rockyou.txt` file is for **password cracking**. You used that one before with gobuster, dumbass
- another p.s: you can use the ```common.txt``` file for learning and practicing. It's easier
>```bash
>/usr/share/wordlists/dirb/common.txt
>```

---

Flags for gobuster command

| Gobuster flag | Desription|
| --- | --- |
| -e | Print the full URLs in your console |
| -u | the target URL | 
| -w | Path to your wordlists | 
| -U and -P | Username and Password for basic authentication | 
| -p [x] | Proxy to use for requests | 
| -c [http cookies] | Specify a cookie for simulating your authentication |


Sample command

```bash
gobuster dir -u http://$192.168.0.1:8080 -w /usr/share/wordlists/dirb/common.txt
```
