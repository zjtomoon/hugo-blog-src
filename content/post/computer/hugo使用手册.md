---
title: "Hugo使用手册"
date: 2021-06-30T15:21:32+08:00
draft: false
---

# hugo博客搭建手册

+ 创建新博文

  ```bash
  hugo new post/name.md
  ```

+ 本地启动预览

  ```
  hugo server -t angels-ladder(theme) -D -w
  ```

  

+ 远程部署

  ```
  hugo --theme=angels-ladder --baseUrl="http://zjtomoon.github.io/"
  ```

  