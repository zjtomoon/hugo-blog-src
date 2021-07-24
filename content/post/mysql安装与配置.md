---
title: "Mysql安装与配置"
date: 2021-06-30T14:31:52+08:00
draft: false
---

## ubuntu安装

```bash
#安装
sudo apt install mariadb-client mariadb-server

```

## centos7 安装

```bash
#安装
sudo yum install mariadb-client mariadb-server
#执行如下命令初始化数据库 设置root密码等信息
mysql_secure_installation
#关闭防火墙，使得外网可以访问数据库
sudo systemctl stop firewalld
#(optional)
#sudo systemctl disable firewalld
```



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





