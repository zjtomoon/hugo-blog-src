---
title: "Rust离线版安装和编辑器配置"
date: 2021-07-01T15:28:07+08:00
draft: false
---

# rust离线版安装

+ 1、解压离线包

```bash
  tar -zxvf rust-1.34.2-x86_64-unknown-linux-gnu.tar.gz -C ~/sdks
```

  

+ 2、进入解压包执行.install.sh

```bash
  sudo ./install.sh
```

  

+ 3、验证安装是否成功

```bash
  rustc --version
  cargo --version
```

  

# 配置编辑器vscode

+ 1、首先下载对应版本的源码解压

```bash
tar -zxvf rustc-1.34.2-src.tar.gz -C ~/sdks
```



+ 2、配置环境变量

```bash
vim ~/.bashrc
```

```bash
export RUST_SRC_PATH=/home/alex/software/rustc-1.34.2-src/src
```

+ 3、初始化环境变量

```bash
source ~/.bashrc
```

+ 4、vscode安装rust(rls)插件并禁用rustup(勾选`disable rustup`选项)

# 配置编辑器emacs

+ 1、克隆emacs配置，使用lsp-mode实现代码补全

```bash
https://gitee.com/zjtomoon/my-emacs-config.git
```

+ 2、复制init.el到~/.emacs.d

```bash
cp my-emacs-config/init.el ~/.emacs.d
```

+ 3、打开emacs自动加载插件，加载完毕后执行emacs命令

```bash
	M-x package-install ret
  	rust-mode ret
```

  