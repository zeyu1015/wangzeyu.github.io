---
title: centos 7 安装docker
date: 2023-03-03T11:18:33Z
lastmod: 2023-03-08T13:50:11Z
tags: [Docker]
---

# centos 7 安装docker

一、环境准备

Docker 支持以下的 CentOS 版本：

　　1、Docker 运行在 CentOS 7(64-bit)上要求系统为 64 位，系统内核版本为 3.10 以上

　　2、Docker 运行在 Centos 6.5 或者更高的版本上，要求系统为 64 位，系统内核版本为 2.6.32-431 或者更高版本

二、查看 centos 版本和内核版本：

　　1、先查看自己的系统版本：cat /etc/centos-release

三、docker 安装步骤

　　1、安装系统依赖工具

```bash
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```

　　2、yum 的配置管理，添加 docker 的软件源地址

```bash
sudo yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```

       3、更新 yum 缓存

```bash
sudo yum makecache fast
```

       4、可以查看所有仓库中所有 docker 版本，并选择特定版本安装

```bash
yum list docker-ce --showduplicates | sort -r
```

       5、选择 docker 版本安装，由于 repo 中默认只开启 stable 仓库，这里安装的是最新版本

```bash
sudo yum install docker-ce 或者指定版本sudo yum install docker-ce-17.12.1.ce
```

　    6、启动 docker 服务

```bash
sudo systemctl start docker
```

　    7、加入开机启动项

```bash
sudo systemctl enable docker
```

　     8、查看 docker 版本

```bash
docker version
```

‍
