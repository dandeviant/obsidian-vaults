What to install:
> ```bash 
> sudo apt-get install libmysqlclient-dev
> ``` 

Compiling C MySQL program
> ```bash
> gcc cserver.c `mysql_config --cflags` `mysql_config --libs`
>```