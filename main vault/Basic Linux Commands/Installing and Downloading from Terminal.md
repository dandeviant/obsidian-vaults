how to install stuffs in linux terminal
---------------

Basic Installing

> ```bash
> sudo apt-get install <whatever/you/like>
> ```


Installing multiple items

> ```bash
> $ sudo apt-get install \
   > ca-certificates \
   > curl \
  > gnupg \
  > lsb-release
> ```

Assign output of terminal to a variable
```bash
variable = $(command)
```

Sample (I downloaded rustscan .deb file in this and trying to install it)
>```bash
>$rustscan = $(ls | grep rustscan)
>
>sudo apt-get install $rustscan
>```

