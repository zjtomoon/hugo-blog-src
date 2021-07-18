---
title: "Wsl Suse Linux镜像配置"
date: 2021-07-18T09:43:35+08:00
draft: false
---

# 1、禁用原来的镜像源

```bash
sudo zypper mr -da
```

# 2、 新增国内zypper源

```bash
sudo zypper ar https://mirror.bjtu.edu.cn/opensuse/update/leap/42.3/non-oss/ update-repo-no-oss-bjtu
sudo zypper ar https://mirror.bjtu.edu.cn/opensuse/update/leap/42.3/oss/ update-repo-oss-bjtu
sudo zypper ar https://mirror.bjtu.edu.cn/opensuse/distribution/leap/42.3/repo/oss/ dis-repo-oss-bjtu
sudo zypper ar https://mirror.bjtu.edu.cn/opensuse/distribution/leap/42.3/repo/non-oss/ dis-repo-non-oss-bjtu

```

# 3、刷新镜像源

```bash
sudo zypper refresh
```

# 4、使用zypper包管理工具

```
sudo zypper in cmake
```

