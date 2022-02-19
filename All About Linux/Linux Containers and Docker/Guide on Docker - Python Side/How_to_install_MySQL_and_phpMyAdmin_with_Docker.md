
**1. Requirements**

>-   Install Docker - On Windows or Mac, go to: [https://docs.docker.com/engine/installation/](https://docs.docker.com/engine/installation/)
> - On Linux, just run on terminal:
> `curl -sSL https://get.docker.com/ | sh` 
   

**2. Create a Docker network**

The phpMyAdmin most communicate each other so is necessary create a Docker network and add both into it.

>```bash
># Create the network called "asgard"
>docker network create itt440-docker
>```

**3. Create the MySQL container**

The following command will create a MySQL container. Below I'll show you the params. Change as you wish and adapt to your use.

>```bash
sudo docker run -d --name itt440-mysql --network itt440-docker -e MYSQL_ROOT_PASSWORD="123" -v /opt/mysql:/var/lib/mysql -p 3306:3306 mysql:8.0.12
> ```

**4. Create the phpMyAdmin container**

The following command will create a phpMyAdmin container. You will need to link to MySQL container, so the phpMyAdmin can connect and access databases.

> ```bash
> # Create phpMyAdmin container
> # # PMA_HOST is the IP or domain of the MySQL server,
> # so we can use the MySQL container name as the domain
> # cause the Docker network create the route as a DNS server.
> 
> sudo docker run -d --name itt440-phpmyadmin 
> --network itt440-docker -e PMA_HOST=itt440-mysql 
> -p 8080:80 phpmyadmin/phpmyadmin:latest
> ```

**Access the database**

Go to the browser and access the phpMyAdmin. The default user is “root” and password will the password set on MySQL container creation.

To get access to phpMyAdmin, go to: [http://localhost:8080/](http://localhost:8080/)  
In my case, I was running on a Virtual Machine and I was accessing it from a different IP address.
