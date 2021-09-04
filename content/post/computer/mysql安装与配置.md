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
#启动mysqld
sudo systemctl start mysqld/mariadb
sudo systemctl enable mysqld/mariadb
#执行如下命令初始化数据库 设置root密码等信息
mysql_secure_installation
#关闭防火墙，使得外网可以访问数据库
sudo systemctl stop firewalld
#(optional)
#sudo systemctl disable firewalld
```

## 解压版安装

```bash
#解压文件
tar -zxvf  mariadb-10.0.10-linux-x86_64.tar.gz -C ~/sdks
#移动文件至指定目录
mkdir -p /usr/local/mariadb
mv mariadb-10.0.10-linux-x86_64/* /usr/local/mariadb
#进入/usr/local/mariadb
#重命名my.cnf为my.cnf.bak，并将mariadb/support-files下的my-small.cnf文件拷贝至etc并命名为my.cnf
cp my-small.cnf /etc/my.cnf
#修改my.cnf文件在[mysqld]标签下添加basedir属性
basedir=/usr/local/mariadb
#初次安装，需要创建mysql用户和组，并给当前目录赋值
groupadd mysql
useradd -r -g mysql -s /sbin/nologin mysql
chown -R mysql .
chgrp -R mysql .
#执行初始化安装
./scripts/mysql_install_db  --user=mysql
#调整权限
chown -R root .
chown -R mysql data/
#添加mysql到服务目录
cp support-files/mysql.server /etc/init.d/mysqld
#第一次安装需要启动服务
/etc/init.d/mysqld start
#初始化操作
systemctl start mysqld
systemctl enable mysqld
#创建root密码
mysqladmin -u root password '123'
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





