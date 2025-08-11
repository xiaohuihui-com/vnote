# mysql环境搭建
```shell
mysqld  -install
mysqld  --initialize
net start mysql
net stop mysql

```
```shell
mysqld --skip-grant-tables
```
```shell
# 登录MySQL后，重置root密码
mysql -u root -p
```
```shell
USE mysql;
UPDATE user SET authentication_string=PASSWORD('new_password') WHERE User='root';
FLUSH PRIVILEGES;
```