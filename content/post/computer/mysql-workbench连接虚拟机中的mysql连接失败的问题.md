---
title: "Mysql Workbench连接虚拟机中的mysql连接失败的问题"
date: 2021-07-07T11:23:33+08:00
draft: false
---

# 创建对外网开放的mysql用户

```sql
create user 'tom' @ '%' identified by '123';
grant all privileges on *.* to 'tom'@'%' identified by '123';
FLUSH PRIVILEGES;
```

# 修改my.cnf

```bash
vim /etc/mysql/my.cnf
```

```bash
##注释bind-address
#bind-address		127.0.0.1
bind-address		0.0.0.0
```

# 重启mysql

```bash
sudo /etc/init.d/mysql restart
```

