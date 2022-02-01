Installing Docker manager

>```bash
>$ sudo apt install docker.io
>```

Testing Docker usability
> ```bash
> $ sudo docker run hello-world
> ```

# Managing Docker Images

**Searching for Docker images**
>```bash
>$ docker search (KEYWORD)
>``````

**Pulling Docker images**
>```bash 
>$ docker pull (KEYWORD)
>```

<details>
<summary>Side Note on pulling</summary>
This step is necessarily skippable since the "docker run" command will automatically pulls the needed image and runs it
 </details>

---

# Managing/Navigating Docker

**List out all pulled images**
>```bash
>$ docker images
>```

**Run Docker Container using image**
>```bash
>$ docker run ubuntu
>```
>```-it``` = keeps the container running even without processes
>```bash
>$ docker run -it ubuntu /bin/bash
>```
<details>
<summary>Side Note on running Docker</summary>
If you knew what images you wanna use, but haven't pulled them for local use yet, you can just straight pull and run an image using this command
 </details>

**List all running Containers**
>Basic
>```bash
>$ docker ps
>```
>```-a``` = List all processes, including the exited ones




