---
title: Docker - 001 优雅的配置代理
date: 2024-12-19T15:57:08.001Z
tags: [Docker]
comments: true
summary: 果然还是离不开魔法梯子啊
---

> 因为某不可力抗的原因，想要优雅的使用 Docker 就得为其配置一下代理

那么，有几种方式：

1. 拉取镜像时代理

通俗一点，就是执行 `docker pull` 的时候使用代理。

**准备配置文件：**

```shell
sudo mkdir -p /usr/lib/systemd/system/docker.service.d
sudo touch /usr/lib/systemd/system/docker.service.d/proxy.conf
```

`proxy.conf` 文件名不强制要求。

**添加代理设置：**

```shell
cat > /usr/lib/systemd/system/docker.service.d/proxy.conf << EOF
[Service]
Environment="HTTP_PROXY=http://proxy.example.com:8080/"
Environment="HTTPS_PROXY=http://proxy.example.com:8080/"
Environment="NO_PROXY=localhost,127.0.0.1,.example.com"
EOF
```

2. 容器运行时代理

容器运行时，容器内部的服务不会使用外部代理，执行软件源更新时巨慢无比，看来这里也需要进行配置。

查看[参考](#参考)

3. 容器构建时代理

构建容器时，通常也会慢得离谱，也需要进行代理设置。

查看[参考](#参考)

## 参考

1. [CharyGao - 博客园](https://www.cnblogs.com/Chary/p/18096678)
