---
title: "Ubuntu编译安装redis"
date: 2021-07-03T10:59:19+08:00
draft: false
---

# 编译redis

```bash
tar -zxvf redis-5.0.1.tar.gz -C ~/software
cd ~/software/redis-5.0.1/
## compile
make
## test 
make test
```

## 安装redis

```bash
#make PREFIX=/some/other/directory install
sudo make install
```

# 开启redis服务

```bash
cd utils
./install_server.sh
```

