### Compress and decompress with gzip

Compress
> ```bash
> gzip namefile.extension
> ```
> Product: ```namefile.extension.gz```

Decompress

>```bash
>gunzip namefile.extension.gz
>```
>
Product: ```namefile.extension```

Sample
```bash
┌──(kali㉿kali)-[~/Desktop]
└─$ gzip trash.txt     
                                                                                                               
┌──(kali㉿kali)-[~/Desktop]
└─$ ls
trash.txt.gz
                                                                                                               
┌──(kali㉿kali)-[~/Desktop]
└─$ gunzip trash.txt   
                                                                                                               
┌──(kali㉿kali)-[~/Desktop]
└─$ ls
trash.txt
```
