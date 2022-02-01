# Just the basics on how to handle passwords and everything

Home: [[(Main) Basic Linux Commands]]

---

**Change current user password**

> ```bash
> passwd
> ```

**Change root password**
> ```bash
> sudo passwd root
> ```

**Add a New Group**
>```text
>$ sudo groupadd new_group
>```

**Add an Existing User Account to a Group**
>```text
>$ usermod -a -G examplegroup exampleusername
>```

**Change a User’s Primary Group**
>```text
>$ usermod -g groupname username
>```