---
title: Overleaf建站
description: 踩的一些坑
date: 2025-01-09
lastmod: 2025-01-09
author: Vincent Ice
avatar: /me/xx.jpg
cover: cover.jpg
categories:
    - 杂
tags: 
    - Overleaf
---

> 项目官网: [overleaf/overleaf: A web-based collaborative LaTeX editor](https://github.com/overleaf/overleaf)
>
> 安装项目: [overleaf/toolkit](https://github.com/overleaf/toolkit/)

参考官方[快速入门指南](https://github.com/overleaf/toolkit/blob/master/doc/quick-start-guide.md)基本就没啥流程问题

这里简述几个我遇到的问题

## sharelatex镜像下载

由于这个包在国内镜像源都没有镜像, 所以比较难下载, 在找了一圈攻略后找到了一个国内的镜像站有

[docker.io/sharelatex/sharelatex 项目](https://docker.aityp.com/r/docker.io/sharelatex/sharelatex)

**我如果先运行`bin/up`报错后再下载镜像源还是会报错, 先下载再运行`bin/up`才没问题**


## 配置问题

### overleaf.rc

有官方[设置介绍](https://github.com/overleaf/toolkit/blob/master/doc/overleaf-rc.md)

需要改动的

- `OVERLEAF_LISTEN_IP`服务器端改成`0.0.0.0`
- `OVERLEAF_PORT`改为任意一个没被占用的端口
- `SIBLING_CONTAINERS_ENABLED`这个默认值是`true`但是社区版只能`false`, 需要改动一下

### variables.env

这里是docker的参数, 自己用甚至完全不用改

- `OVERLEAF_SITE_URL`可以改为网站/公网IP, 方便连接分享
- `OVERLEAF_ADMIN_EMAIL`站长邮箱
- 邮箱SMTP相关服务

## TexLive完整版安装

我这里完全参考[官方教程](https://github.com/overleaf/toolkit/blob/master/doc/ce-upgrading-texlive.md)就成功了~~看别的教程要换源之类的, 我看没换能下得了就上床睡觉了, 醒来就装好了~~

由于完整版巨大无比, 建议用`screen`或者`tmux`之类支持终端与会话分离的软件, 以防半途寄了重新装

### 更新宏包

在docker命令行中:

查看所有更新

```shell
tlmgr update --list
```

更新

```shell
tlmgr update --self --all
```

如果遇到更新宏包过程中，某一个宏包更新失败，可以使用指令继续更新

```shell
tlmgr update --reinstall-forcibly-removed --all
```

## XeLaTex修复

```bash
docker exec -it sharelatex bash
apt update
apt install -y texlive-xetex texlive-latex-extra texlive-science
```

## 测试并保存docker镜像

测试一下都正常安装, 用起来没问题就可以保存新的docker镜像了

参考[官方文档](https://github.com/overleaf/toolkit/blob/master/doc/ce-upgrading-texlive.md#saving-your-changes)的`#saving-your-changes`部分

## Github自动拉取项目文件

使用的项目为[subhamX/overleaf_sync_with_git](https://github.com/subhamX/overleaf_sync_with_git)

需要注意的点是Cookie每个站可能不一样, 需要根据自己的站修改一下, 见[Issue#10](https://github.com/subhamX/overleaf_sync_with_git/issues/10)

原作者提供的是基于`https`访问的, 如果你的服务器没有ssl证书的话得自己改一下使用`http`访问




参考:
1. [overleaf服务器搭建 | bilibili](https://www.bilibili.com/video/BV1bcmMYwEQJ/?share_source=copy_web&vd_source=5577ef15250ee11ef3b76c4d06a40442) 
2. [Docker部署Overleaf包含中文字体与全套texlive镜像_overleaf](https://blog.csdn.net/Wrm244/article/details/128567900)
3. [LaTeX安装 & 宏包升级 - 知乎](https://zhuanlan.zhihu.com/p/210303123)
4. [如何免费畅快使用阿里云ECS搭建私有Overleaf论文写作服务](https://blog.csdn.net/fyf2007/article/details/143648561)
