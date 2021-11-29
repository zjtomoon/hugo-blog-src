---
title: "Jupyter安装和配置"
date: 2021-11-29T21:04:24+08:00
draft: false
---

# 安装

+ 安装jupyter

```bash
pip install jupyter notebook
```



+ 安装扩展插件

```bash
pip install jupyter_contrib_nbextensions
```



+ 安装主题样式工具包

```bash
pip install jupyterthemes
```

# 配置

+ 配置jupyter代码补全

```bash
jupyter contrib nbextension install --user
pip install jupyter_nbextensions_configurator
jupyter nbextensions_configurator enable --user
#勾选Nbextensions中的Hinterland
```



+ 配置主题

```bash
# 显示主题
jt -l 
# 切换主题
jt -t onedork
#切回默认主题
jt -r
```

