**Source:** 
How To Change Username in Kali Linux - 
https://techdhee.in/change-username-in-kali-linux/

---
### How to change username

1. Set root password
>```bash
>$ sudo passwd root
>```
3. Restart machine 
4. Login with root
5. Create new user, rename old home directory with new ones

>```bash
>$ usermod -l newusername -d /home/newusername -m oldusername
>```

5. Create a symbolic link from /home/newusername to /home/oldusername

>```bash
>$ ln -s /home/newusername /home/oldusername
>```

6. Change the display name or full name (unnecessary)

>```bash
>chfn -f "FIRSTNAME LAST NAME"  newusername
>```

7. You can now restart the machine and login with the new username