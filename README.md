#### pkgestmaria


- cp1

ubuntu
```
sudo apt-get install mariadb-server
```
centos:  
```
sudo yum install MariaDB-server MariaDB-client  
sudo /etc/init.d/mysql start
```

maria log file:
```
/var/lib/mysql/      //linux
C:\Program Files\MariaDB\data\   //windows
/usr/local/var/mysql/          //osx
```

config file location:
```
/etc/my.cnf.d/ 
/etc/mysql/conf.d/
```

print defaults:
```
mysql --print-defaults
```

show all options(too long)
```
mysqld --no-defaults --help --verbose
```

restart maria  
windows
```
sc stop mysql
sc start mysql
```
linux
```
/etc/init.d/mysql reload
service mysql reload
```

using config file log in
```
mysql --defaults-file=/path
```
add contents:
```
[client]
user = user
password=password
```

- cp4
show grants
```
SHOW GRANTS FOR 'user'@'localhost';
```

change password
```
SET PASSWORD FOR 'user'@'%' = PASSWORD('password');
```

```
\G = ;
SHOW CREATE TABLE employees \G
```

describe column
```
DESCRIBE table column
```

- cp6
insert from other tables
```
INSERT INTO table1 (a, b, c)
SELECT a, b, c
FROM table2;
```

load local file  
```
LOAD DATA INFILE '/path' INTO TABLE table (a, b, c);
```


- cp7
```
TIMESTAMPDIFF
CURDATE
```
Ex:
```
SELECT AVG(TIMESTAMPDIFF(YEAR,birthday,CURDATE())) 
```

- cp8
mysqlbinlog

export tab indented files.
```
mysqldump --tab /dest/ -u root -p db table
```
this will generate two files. table.sql table.txt  

mysqlimport
```
mysqlimport --local -u root -p test /dest/table.txt
```

