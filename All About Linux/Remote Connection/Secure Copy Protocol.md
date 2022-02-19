SCP

1. Copy remote target files to local current directory

>```bash
scp username@ip_address:/home/username/filename .
>```

2. Copy files to remote target directory
>```bash
scp filename username@ip_address:/home/username
>```

3. Copy remote directory to local machine
>```bash
scp -r source_dir username@ip_address:/home/username/target_dir
>```