---
title: "Mysql安装与配置"
date: 2021-06-30T14:31:52+08:00
draft: false
---

## ubuntu安装

安装sudo apt install mariadb-client mariadb-server查看配置sudo vim /etc/mysql/
debian.cnf进入root数据库sudo mysql 输入系统root密码进入my
sql root用户数据库

## 添加用户


```bash
 1. root权限登录 mysql -u root -p
 2.添加用户  
 配置用户本地 IP 访问 localhost, 127.0.0.1
 create user 'username'@'localhost' identified by 'password';
 配置用户外网 IP 访问
 create user 'username'@'%' identified by 'password'; 
 刷新权限
 FLUSH PRIVILEGES;
 用户权限权限列表:
 grant all privileges on *.* to 'username'@'%' identified by 'password';
 grant   SELECT,DELETE,UPDATE on *.* to 'username'@'%' identified by 'password';
 刷新权限FLUSH PRIVILEGES;
```





