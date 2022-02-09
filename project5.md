# IMPLEMENTING A CLIENT SERVER ARCHITECTURE USING MYSQL DATABASE MANAGEMENT SYSTEM

## Configure a server for mysql server

Update Ubuntu

`sudo apt update`

![](images/1.png)

Upgrade Ubuntu

`sudo apt upgrade`

![](images/2.png)

Install mysql server

`sudo apt install mysql-server`

![](images/3.png)

`sudo mysql_secure_installation`

![](images/4.png)

Switch to mysql console

`sudo mysql`

![](images/5.png)

Create user in mysql

`mysql>  CREATE USER 'remote_user'@'%' IDENTIFIED WITH mysql_native_password BY 'Password12345.';`

![](images/6.png)

Create database

`mysql> CREATE DATABASE test_db;`

![](images/7.png)

Grant sudo privileges

`mysql> GRANT ALL ON test_db.* TO 'remote_user'@'%' WITH GRANT OPTION;`

![](images/8.png)

Flush privileges

`mysql> FLUSH PRIVILEGES`

![](images/9.png)

## Change bind address 0.0.0.0

Open and edit mysqld.cnf file

`sudo vim /etc/mysql/mysql.conf.d/mysqld.cnf`

![](images/10.png)

![](images/11.png)

Restart mysql

`sudo systemctl restart mysql`

# CREATE CLIENT SERVER

Update Ubuntu 

`sudo apt update`

![](images/12.png)

Upgrade Ubuntu

`sudo apt upgrade`

![](images/13.png)

Install mysql-client

`sudo apt-get install mysql-client`

![](images/14.png)

Get client server ip 

` ip addr show`

![](images/ip.png)

Add ip to ec2 inbound rules

![](images/15.png)

In client server connect to mysql

` sudo mysql -u remote_user -h 172.31.86.133 -p`

![](images/16.png)

Test mysql connection

`mysql>Show databases;`

![](images/17.png)
