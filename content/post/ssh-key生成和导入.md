---
title: "Ssh Key生成和导入"
date: 2021-06-30T16:35:56+08:00
draft: true
---

# ssh-key生成并导入github的方法

+ 1、设置git用户名和邮箱

  ```bash
   git config --global user.name "yourusername"
   git config --global user.email "youremail"
  ```

  

+ 2、生成密钥

  ```bash
  ssh-keygen -t rsa -C "emailname@qq.com"
  ```

  

+ 3、添加SSH key到github账户

+ 4、测试SSH key是否设置成功

  ```bash
  ssh -T git@github.com
  ```

+ 5、更改.git/config文件为ssh形式