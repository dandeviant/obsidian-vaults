**Login to MySQL container**

```bash
sudo docker exec -it itt440-mysql mysql -uroot -p
```

**Create Database**

```mysql
create database users;
```

**Select Databse**
```mysql
use users;
```

**Create table**
```mysql
create table user(
user varchar(200),
points int,
datetime_stamp varchar(100)
);
```

**Insert row into table users**
```mysql
INSERT INTO user(user,points, datetime_stamp) VALUES ("Michael Morbius", 666, "12 Feb");
```

**Check table properties and row inserted**
```mysql
mysql> SELECT * FROM user;
+-----------------+--------+----------------+
| user            | points | datetime_stamp |
+-----------------+--------+----------------+
| Michael Morbius |    666 | 12 Feb         |
+-----------------+--------+----------------+
1 row in set (0.00 sec)

```

**Update row**
```mysql
UPDATE user 
SET user="pyclient", 
points="22",
datetime_stamp="feb 12" 
WHERE user="python-client";
```

> Update points
> ```mysql
> UPDATE user 
> SET origin_server="Python Server" 
> WHERE user in ("Morbius", "Luke Fox");
> ```