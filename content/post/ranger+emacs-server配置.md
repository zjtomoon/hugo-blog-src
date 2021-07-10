---
title: "Ranger+emacs Server配置"
date: 2021-07-10T07:56:10+08:00
draft: false
---

# 安装pypi版ranger

```bash
sudo pip3 install ranger-fm
```

# 开启emacs服务

```bash
emacs --daemon
# 开启emacs服务，把emacs配置文件加载到内存中
```

# 设置emacs为默认编辑器

```bash
vim ~/.bashrc
##添加一行
export EDITOR=emacsclient
source ~/.bashrc
```

