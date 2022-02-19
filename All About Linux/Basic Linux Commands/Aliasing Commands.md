## Aliasing custom commands
---

  
So, basically the path for the shell config files varies, depending on the OS and shell used.
To see what shell is running, use this command
```bash 
ps -p $$
```

And you need to find the path of the shell config file. Use `ls -a` 
For example, Kali Linux used ZSH shell, so the config file path is:

```bash
/home/kali/.zshrc
```

while Ubuntu used bash shell, which is in
```bash
/home/mattdaniel/.bashrc
```

After adding the custom alias,  restart the shell running.

---
Syntax for adding alias

```bash
alias <aliasname>="<shell command>"
```
OR
```bash
<aliasname> (){
<command 1> <variable>
<command 2>
}
```

Samples of aliases are as below:

---


**My Aliases for ZSH and Bash**

- mkcd
Hex (He is an American friend of mine from TryHackMe) gave me his idea of making a directory and change current working path to the newly-created one. Why I never thought of this tho? It's so fuckin good

```bash
mkcd (){
mkdir $1
cd  $1
}
```

- motd - To display custom motd message
```zsh
motd (){
echo "Fuck you Matt"
echo "Peace"
}
```

- motd2 - the good motd
```bash
alias motd2="echo 'Hello Matt...' "
```
