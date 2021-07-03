---
title: "Docker和k8s安装"
date: 2021-07-03T10:57:10+08:00
draft: false
---

# ubuntu安装新版docker

## 添加镜像源

+ 更新镜像源

```bash
sudo apt-get update
```

```bash
sudo apt-get install \
	apt-transport-https \
    ca-certificates \
    curl \
    gnupg \
    lsb-release
```

+ 添加Docker官方key

```bash
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
```

```bash
echo \
  "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```



## 安装Docker

```bash
 sudo apt-get update
 sudo apt-get install docker-ce docker-ce-cli containerd.io
```

```bash
apt-cache madison docker-ce
```

```bash
sudo apt-get install docker-ce=<VERSION_STRING> docker-ce-cli=<VERSION_STRING> containerd.io
```

```bash
sudo docker run hello-world
```




# ubuntu安装k8s

## 下载最新版kubernetets

```bash
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

## 安装kubectl

```bash
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl

```

```bash

## 验证安装

​```bash
kubectl version --client
```

## 用包管理器安装

+ 1. 更新 `apt` 包索引，并安装使用 Kubernetes `apt` 仓库锁需要的包：

   ```bash
   sudo apt-get update
   sudo apt-get install -y apt-transport-https ca-certificates curl
   ```


+ 2. 下载 Google Cloud 公开签名秘钥：

   ```bash
   sudo curl -fsSLo /usr/share/keyrings/kubernetes-archive-keyring.gpg https://packages.cloud.google.com/apt/doc/apt-key.gpg
   ```

+ 3. 添加 Kubernetes `apt` 仓库：

   ```bash
   echo "deb [signed-by=/usr/share/keyrings/kubernetes-archive-keyring.gpg] https://apt.kubernetes.io/ kubernetes-xenial main" | sudo tee /etc/apt/sources.list.d/kubernetes.list
   ```


+ 4. 更新 `apt` 包索引，使之包含新的仓库并安装 kubectl：

   ```bash
   sudo apt-get update
   sudo apt-get install -y kubectl
   ```



