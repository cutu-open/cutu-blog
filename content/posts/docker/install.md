---
title: "Install"
date: 2020-02-06T12:22:25+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","Docker"]
categories: ["Docker"]
series: ["Tutorial"]
description: "安装Docker"
title: "Docker-安装"
---

## CentOS7
```shell
yum update

yum install -y yum-utils device-mapper-persistent-data lvm2

yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo

yum list docker-ce --showduplicates | sort -r

yum install docker-ce[-版本号]
# 配置镜像加速器
# https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors
mkdir -p /etc/docker

tee /etc/docker/daemon.json <<-'EOF'
{ 
   "registry-mirrors": ["输入你自己控制台此处的地址"]
}
EOF

systemctl daemon-reload

systemctl start docker

systemctl enable docker

```


