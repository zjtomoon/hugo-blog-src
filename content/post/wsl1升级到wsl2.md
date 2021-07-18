---
title: "Wsl1升级到wsl2"
date: 2021-07-18T11:13:20+08:00
draft: false
---

# 1、启用"虚拟机平台"

> 在“控制面板\所有控制面板项\程序和功能”中选择“启用或者关闭Windows功能”，勾选对应选项即可：



# 2、安装WSL2内核

+ 下载地址 https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

# 3、 将安装的wsl1切换到wsl2

```powershell
wsl --set-version SLES-12 2
## 经过一段时间后切换成功
```

# 4、 验证是否升级成功

```powershell
wsl --list --verbose
```

