---
title: Docker - 000 快速安装 Docker
date: 2024-12-19T15:57:08.000Z
tags: [Docker]
comments: true
summary: 多种快速安装方法！
---

> 就喜欢别人写好的脚本（:不是

## 安装方式

1. [脚本快速安装（可国内代理）](#方式一快速安装)
2. [二进制安装（TODO）](#方式二离线安装)

## 方式一：快速安装

### 脚本

很简单，打开终端（例如 Terminal）, 输入：

```shell
bash <(curl -sSL https://linuxmirrors.cn/docker.sh)
```

按需选择，等待即可！优雅！

**备注：** 自 `v2` 版本之后 `docker-compose` 作为 `docker cli` 的一部分不需要在单独安装！使用方式从 `docker-compose` 修改为 `docker compose`！

### 命令选项

截取自 [官方文档](https://linuxmirrors.cn/other/#%E5%91%BD%E4%BB%A4%E9%80%89%E9%A1%B9)

| 名称                   | 含义                                | 选项值            |
| ---------------------- | ----------------------------------- | ----------------- |
| `--source`             | 指定 `Docker CE` 源地址（域名或IP） | 地址              |
| `--source-registry`    | 指定镜像仓库地址(域名或IP)          | 地址              |
| `--codename`           | 指定 Debian 系操作系统的版本代号    | 代号名称          |
| `--install-latest	`     | 是否安装最新版本的 `Docker Engine`  | `true` 或 `false` |
| `--close-firewall`     | 是否关闭防火墙                      | `true` 或 `false` |
| `--clean-screen`       | 是否在运行前清除屏幕上的所有内容    | `true` 或 `false` |
| `--ignore-backup-tips` | 忽略覆盖备份提示（即不覆盖备份）    | 无                |

软件源完整格式 `<WEB协议>://<软件源地址（域名或IP）>/<软件源仓库（路径）>`

官方网站还提供了常见服务的一键换源命令，如：

**NPM**

淘宝源：

```shell
npm config set registry https://registry.npmmirror.com/
```

腾讯云：

```shell
npm config set registry https://mirrors.tencent.com/npm/
```

**PYPI**

阿里云：

```shell
pip3 config set global.index-url https://mirrors.aliyun.com/pypi/simple/
```

腾讯云：

```shell
pip3 config set global.index-url https://mirrors.tencent.com/pypi/simple/
```

中科大

```shell
pip3 config set global.index-url https://pypi.mirrors.ustc.edu.cn/simple/
```

## 方式二：离线安装

TODO

## 致谢

[Linux mirrors](https://linuxmirrors.cn/other/)
