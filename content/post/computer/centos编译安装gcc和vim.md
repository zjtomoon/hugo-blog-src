---
title: "Centos编译安装gcc和vim"
date: 2021-11-09T14:12:50+08:00
draft: false

---

# 编译安装新版gcc

> 前提条件：gcc版本4.8.1以上

+ 1、安装必要环境

  ```bash
  sudo yum install zlib-devel
  sudo yum install glibc-devel
  sudo yum install glibc-devel.i686
  sudo  yum install libstdc++-devel
  sudo  yum install libstdc++-devel.i686
  
  ```

  

+ 2、执行configure命令生成makefile

  ```bash
  ./configure --enable-bootstrap --enable-languages=c,c++ --enable-threads=posix --enable-checking=release --enable-multilib --with-system-zlib
  # 不声明prefix则默认覆盖安装
  ```

  

+ 3、执行编译和安装

  ```bash
  make 
  sudo make install
  ```

  

# 编译安装vim

+ 1、安装必要依赖

  ```bash
  sudo yum install ncurses-devel.x86_64
  ```

  

+ 2、编译安装

  ```bash
  ./configure
  make 
  sudo make install
  ```

  

