0. Run MySQL container
```bash
sudo docker exec -it itt440-mysql mysql -uroot -p
```

1. **Create Ubuntu C server container and Link to MySQL container**

```bash
sudo docker run -t -d --name itt440-cserver --network itt440-docker --link itt440-mysql ubuntu:latest /bin/bash
```

1. **Log into C server with shell**
```bash
sudo docker exec -it itt440-cserver bash
```

2. **Create Ubuntu C client container and Link to Python server container**
```bash
sudo docker run -t -d --name itt440-cclient --network itt440-docker --link itt440-cserver ubuntu:latest /bin/bash
```
2. **Log into C client with shell**
```bash
sudo docker exec -it itt440-cclient bash
```

Things to install in container
```bash
apt-get update
```

```bash
apt install net-tools \
iputils-ping \
nano \
gcc
```

> - gcc
> - net-tools
> - iputils-ping
> - nano / vim / ee


