---
title: "MongoDB学习笔记"
date: 2021-06-30T14:32:54+08:00
draft: false
---

<center> Mongo学习笔记</center>

## docker安装mongo

### 1、取最新版的 MongoDB 镜像

这里我们拉取官方的最新版本的镜像：

```
$ docker pull mongo:latest
```

[![img](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo3.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo3.png)

### 2、查看本地镜像

使用以下命令来查看是否已安装了 mongo：

```
$ docker images
```

[![img](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo4.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo4.png)

在上图中可以看到我们已经安装了最新版本（latest）的 mongo 镜像。

### 3、运行容器

安装完成后，我们可以使用以下命令来运行 mongo 容器：

```
$ docker run -itd --name mongo -p 27017:27017 mongo --auth
```

参数说明：

- **-p 27017:27017** ：映射容器服务的 27017 端口到宿主机的 27017 端口。外部可以直接通过 宿主机 ip:27017 访问到 mongo 的服务。
- **--auth**：需要密码才能访问容器服务。

[![img](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo5.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo5.png)

### 4、安装成功

最后我们可以通过 **docker ps** 命令查看容器的运行信息：

[![img](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo6.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo6.png)

接着使用以下命令添加用户和设置密码，并且尝试连接。

```
$ docker exec -it mongo mongo admin
# 创建一个名为 admin，密码为 123456 的用户。
>  db.createUser({ user:'admin',pwd:'123456',roles:[ { role:'userAdminAnyDatabase', db: 'admin'},"readWriteAnyDatabase"]});
# 尝试使用上面创建的用户信息进行连接。
> db.auth('admin', '123456')
```

[![img](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo7.png)](https://www.runoob.com/wp-content/uploads/2016/06/docker-mongo7.png)





## mongodb笔记

