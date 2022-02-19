**Create MySQL Docker container**
> ```bash
sudo docker run -d --name itt440-mysql --network itt440-docker -e MYSQL_ROOT_PASSWORD="123" -v /opt/mysql:/var/lib/mysql -p 3306:3306 mysql:8.0.12
>```

**Login to MySQL container**

>```bash
>sudo docker exec -it itt440-mysql mysql -uroot -p
>```

**Use shell commands from MySQL terminal**
>```mysql
system clear
system apt update
system apt install net-tools
system ifconfig
> ```