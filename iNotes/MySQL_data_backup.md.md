Backup database:
--------------------------------------------
```
mysqldump --opt -h <servername> -u <username> -p<password> <dbname> | gzip > <bkup_file_name.gz>
```
```
mysqldump --opt -h localhost -u root -pRoot@123 test | gzip > bkup.gz; 
```
all database backup:
```
mysqldump -u root -p --all-databases > backup.sql
```

Restore Database:
---------------------------------------------
```
mysql -u <username> -p<password> -e 'CREATE DATABASE <dbname>';
```
```
gunzip < <bkup_file_name.gz> | mysql -u <username> -p<password> <dbname>;
```
```
mysqldump -u root -pRoot@123 --databases txt woldp wp magento> bkp.sql
```
```
mysql -u root -p < backup.sql(filename)
```
restore data using SQL:
```
mysql -u root -pRoot@123 <./bkp.sql
```
Create database table.
```
CREATE TABLE USERS1(ID int(10), name varchar(50), city varchar(50),PRIMARY KEY(id));
```
Insert data into data base table.
```
INSERT INTO USERS1 VALUES(101,'rahul','delhi');  
```
mysql database backup and restore.
```
backup mysql database- mysqldump -u root -p --all-databases > backup.sql(filename give to the backup file) 
```
##### `I want to downgrade php version to 5.6 because I want to test my module in lower version.`
if you have switch you php version old php 5.6.
```error
 ( ! ) Warning: PDO::__construct(): The server requested authentication method unknown to the client [caching_sha2_password] in /home/users/deepak.agrawal/www/html/qlo4/classes/db/DbPDO.php on line _64_
```

for enable phpmyadmin with php5.6  
`vi  /etc/mysql/mysql.conf.d/mysql.cnf`
```
[client]  
default-character-set=utf8  
  
[mysql]  
default-character-set=utf8  
  
[mysqld]  
collation-server = utf8_unicode_ci  
character-set-server = utf8  
default-authentication-plugin=mysql_native_password  
```
![[Pasted image 20240920120607.png]]
restart mysql service.
```
service mysql restart
```
`mysql.conf` file 
update file before line.
```
The MySQL database client configuration file
 Ref to https://dev.mysql.com/doc/refman/en/mysql-command-options.html
[mysq
```
Change password authentication in mysql.
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'webkul';
```
```
ALTER USER 'root'@'localhost' IDENTIFIED WITH caching_sha2_password BY 'webkul';
```
