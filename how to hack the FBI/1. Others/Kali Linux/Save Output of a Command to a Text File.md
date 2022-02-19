Saving outputs of certain commands is always helpful in analyzing them without depending on the tight-ass terminal

How to do that:

Method 1, use tee:
>```bash
>$ ping 127.0.01 -c 4 | tee ping.txt
>```

Method 2, traditional command:
>```bash
>$ ping 127.0.0.1 -c 4 > ping.txt
>```

If you use this method, you will not see the command running in the terminal. You can only view the output when the command is done running. 

**So, try to use tee. It's a good practice**...