---
title: "Ubuntu创建eclipse快捷方式"
date: 2021-07-10T17:13:40+08:00
draft: false
---



**1.** 解压文件

```bash
tar xvf eclipse-SDK-4.2-linux-gtk-x86_64.tar.gz
```

**2.** 把解压后的文件移到相关目录，这里我假设是/opt，并设置好的权限

```bash
mv eclipse /opt/
sudo chown root:root eclipse -R
sudo chmod +r eclipse -R
```

**3.** 创建启动脚本。有很多种不同的实现方法，下面只是其中一种。

```bash
sudo touch /usr/bin/eclipse
sudo chmod 755 /usr/bin/eclipse
sudo vim /usr/bin/eclipse
```

将如下内容写到刚创建的eclipse文件中

```bash
#!/bin/sh
export ECLIPSE_HOME="/opt/eclipse"
$ECLIPSE_HOME/eclipse $*
```

保存，退出。

**4.** 创建Gnome菜单配置文件

```bash
vim /usr/share/applications/eclipse.desktop
```

将如下内容写到刚创建的eclipse.desktop文件

```bash
[Desktop Entry]
Encoding=UTF-8
Name=Eclipse
Comment=Eclipse IDE
Exec=eclipse
Icon=/opt/eclipse/icon.xpm
Terminal=false
Type=Application
Categories=GNOME;Application;Development;
StartupNotify=true
```

保存，退出。

