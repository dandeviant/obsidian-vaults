Aliasing

So, basically the path for the shell config files varies

Kali uses zsh, so the path is

> ```bash
> /home/kali/zshrc
> ```

You gonna need to `ls -a` to find the shell config file.  

And you also need to know what shell you are using. Use this command
> ```bash 
> ps -p $ $ (the dollar sign is close, no space)
> ```

---

Hex (He is a Canadian friend of mine from TryHackMe) gave me his idea of making a directory and change current working path to the newly-created one. 
Why I never thought of this tho? It's so fuckin good

```bash
mkcd (){
mkdir $1
cd  $1
}
```

