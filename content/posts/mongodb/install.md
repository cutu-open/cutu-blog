---
date: 2020-02-09T23:15:06+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","MongoDB"]
categories: ["MongoDB"]
series: ["Tutorial"]
description: "MongoDB安装"
title: "MongoDB安装"
---
# 一、Docker
1. 拉取镜像
```shell
docker pull mongo
```
2. 启动容器
```bash
docker run -it -p 22000:27017 mongo

```


# 连接
```
mongodb://[username:][password@]ip地址:port/[database]
```