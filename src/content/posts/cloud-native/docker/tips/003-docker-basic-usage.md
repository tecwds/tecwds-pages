---
title: Docker - 003 基本使用
date: 2024-12-21T15:57:08.004Z
summary: 就是一些简单的用法
tags: [Docker]
comments: true
draft: false
---

> v2 版本，使用 `docker compose` 替代 `docker-compose`，这下不用单独安装 `compose` 了（:有没有可能早就有了\_

## 基础命令

```shell
# 拉取一个镜像
docker pull images

# 运行一个镜像
docker run images

# 查看系统占用
docker system df

# 删除构建缓存
docker builder prune

# 删除虚悬镜像、构建缓存
docker system prune -a
```
