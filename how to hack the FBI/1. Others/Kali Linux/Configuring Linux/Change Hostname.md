Commands:
```bash
sudo hostnamectl set-hostname newhostname
```

Terminal command with sudo takes a long time - Ask Ubuntu
https://askubuntu.com/questions/322514/terminal-command-with-sudo-takes-a-long-time


**After changing your hostname, you need to update your hostname in the ** ```/etc/hosts``` 

```bash
sudo nano /etc/hosts
```

Add the following
```bash
127.0.0.1        newhostname
```
