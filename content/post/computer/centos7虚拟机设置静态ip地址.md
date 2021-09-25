---
title: "Centos7虚拟机设置静态ip地址"
date: 2021-09-09T15:32:43+08:00
draft: false
---



+ 1、virtual虚拟机设置两种网卡，分别为NAT和host-only模式

+ 2、路径：/etc/sysconfig/network-scripts存在ifcfg-enp0s3，查看配置文件

   ```bash
   cat vim ifcfg-enp0s3
   
    TYPE=Ethernet
    PROXY_METHOD=none
    BROWSER_ONLY=no
    BOOTPROTO=dhcp
    DEFROUTE=yes
    IPV4_FAILURE_FATAL=no
    IPV6INIT=yes
    IPV6_AUTOCONF=yes
    IPV6_DEFROUTE=yes
    IPV6_FAILURE_FATAL=no
    IPV6_ADDR_GEN_MODE=stable-privacy
    NAME=enp0s3
    UUID=bd6e75a6-07f4-40bc-bd4e-2ef269466f4b
    DEVICE=enp0s3
    ONBOOT=yes
   ```

   

+ 3、复制ifcfg-enp0s3，cp ifcfg-enp0s3 ifcfg-enp0s8

  ```bash
  # 修改：
  
  #  BOOTPROTO=dhcp 改为 BOOTPROTO=static
  
  # 　　NAME=enp0s3 改为 NAME=enp0s8  # 这是网卡名，可以用ip a查看
  
  # 　　DEVICE=enp0s3 改为 DEVICE=enp0s8
  
  # 　　UUID 也需要修改，UUID可以重新生成一个，直接在命令行输入 uuidgen，回车就会出现结果，把结果复制过来。
  
  # 添加：
  
  # 　　IPADDR=192.168.56.119 （根据添加的第二网卡的ip范围内即可，默认是 192.168.56.101——192.168.56.255）
  
  # 　　NETMASK=255.255.255.0
  
  # 修改结果为：
  # catifcfg-enp0s8
   TYPE=Ethernet
   PROXY_METHOD=none
   BROWSER_ONLY=no
   BOOTPROTO=staticDEFROUTE=yes
   IPV4_FAILURE_FATAL=no
   IPV6INIT=yes
   IPV6_AUTOCONF=yes
   IPV6_DEFROUTE=yes
   IPV6_FAILURE_FATAL=no
   IPV6_ADDR_GEN_MODE=stable-privacy
   NAME=enp0s8
   UUID=1ef92600-8b30-437c-bb01-e8be0285a29d
   DEVICE=enp0s8ONBOOT=yes
   IPADDR=192.168.56.101
   NETMASK=255.255.255.0
  ```

 

+ 4、重启网络

  ```bash
  sudo systemctl restart network
  ```

  

 

