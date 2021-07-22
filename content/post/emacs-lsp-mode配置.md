---
title: "Emacs Lsp Mode配置"
date: 2021-06-30T14:27:53+08:00
draft: false
---

## go-mode

```bash
go env -w GOPROXY=https://goproxy.io,direct 
go get golang.org/x/tools/gopls@latest
```



## shell-mode

```bash
npm --registry https://registry.npm.taobao.org i -g bash-language-server
```



## rust-mode

```bash
emacs ~/.bashrc
export RUST_SRC_PATH=/home/alex/software/rustc-1.34.2-src/src
```

