---
title: Docker - 002 Docker 配置 TCP
date: 2024-12-19T15:57:08.003Z
tags: [Docker]
comments: true
summary: JetBrains 软件上好用
---

> Docker：本地的不好用吗？Q\_

## 配置方式

检查 `docker` 的服务配置文件，查看 `ExecStart`

```shell
ExecStart=/usr/sbin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock $DOCKER_OPTS
```

存在一个环境变量：`DOCKER_OPTS`，这意味着可以创建对应环境变量配置文件将**选项**传入 `docker` 中。

### 1. 创建环境变量文件

```shell
# 部分目录可能是 /etc/systemd/system/...
mkdir -p /usr/lib/systemd/system/docker.service.d
```

### 2. 写入配置

```shell
cat > /usr/lib/systemd/system/docker.service.d/tcp.proxy << EOF
[Service]
Environment="DOCKER_OPTS='-H tcp://0.0.0.0:2376'"
EOF
```

`2376` 端口可以按需修改

### 3. 重启 Docker

```shell
# 别忘了重载配置文件
systemctl daemon-reload
systemctl restart docker
```
