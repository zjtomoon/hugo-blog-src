---
title: "Ubuntu编译安装emacs"
date: 2021-07-03T10:21:22+08:00
draft: false
---

# 安装必要的依赖

```bash
sudo apt-get install build-essential
```

# 安装emacs需要的依赖

```bash
sudo apt-get build-dep emacs24
```

# 解压emacs源码包

```bash
tar -zxvf emacs-26.1.tar.gz -C ~/softwares
```

# 编译emacs

```bash
cd ~/software/emacs-26.1/
./config
make
##(optionally) install emacs to /usr/local/bin
sudo make install
```

