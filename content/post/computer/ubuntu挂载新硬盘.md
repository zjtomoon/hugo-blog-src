---
title: "Ubuntu挂载新硬盘"
date: 2021-07-20T10:12:49+08:00
draft: false
---

## 1、使用以下命令查看硬盘使用情况

```bash
# 查看硬盘使用情况
df -h
#查询硬盘名称
sudo fdisk -l
```

## 2、先清空需要挂载的硬盘中的内容，把ntfs格式化为ext4

```bash
 sudo mkfs.ext4 /dev/sdbx
```

## 3、查询UUID、type等信息

```bash
 sudo blkid /dev/sdbx
```

## 4、修改开机启动挂载硬盘

```bash
##创建挂载点
mkdir ~/data1
sudo vim /etc/fstab
#添加类似如下的一行
UUID="f9f42ea2-8a3e-499f-a5b3-1ff3d30e01b7" /home/username/data ext4 defaults 0 2
```

## 5、最后执行命令进行挂载即可

```bash
sudo mount -a
```

## 6、重启系统，查看是否挂载成功

+ 右键查看~/data属性 查看容量
