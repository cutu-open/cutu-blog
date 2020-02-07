---
date: 2020-02-06T23:54:31+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","MySQL"]
categories: ["MySQL"]
series: ["Tutorial"]
description: "安装MySQL"
title: "MySQL-安装"
---

# Docker
```bash
docker run -i -p 20000:3306 -e MYSQL_ROOT_PASSWORD=jcx120708 -v /appdata/docker/mysql/data:/var/lib/mysql:rw -v /appdata/docker/mysql/log:/var/log/mysql:rw -v /etc/localtime:/etc/localtime:ro --name mysql_server --restart=always -d mysql
```

