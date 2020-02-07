---
title: "Bydocker"
date: 2020-02-06T17:40:02+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","Zookeeper","Docker"]
categories: ["Zookeeper"]
series: ["Tutorial"]
description: "通过Docker搭建Zookeeper集群"
title: "Docker搭建Zookeeper集群"
---
# 环境
- 系统: CentOS7
- IP: 172.16.82.168
- Docker: Docker version 19.03.5, build 633a0ea
- Zookeeper: 

# 搭建步骤
```bash
mkdir -p /appdata/docker/zookeeper/node1
mkdir -p /appdata/docker/zookeeper/node2
mkdir -p /appdata/docker/zookeeper/node3

# 设置临时变量
machine_ip=172.16.82.128

# node1
docker run -d -p 22181:2181 -p 22182:2888 -p 22183:3888 --name zookeeper_node1 --restart always \ -v /appdata/docker/zookeeper/node1/volume/data:/data \ -v /appdata/docker/zookeeper/node1/volume/datalog:/datalog \ -e "TZ=Asia/Shanghai" \ -e "ZOO_MY_ID=1" \ -e "ZOO_SERVERS=server.1=0.0.0.0:2888:3888 server.2=172.16.82.128:22185:22186 server.3=172.16.82.128:22188:22189" zookeeper

# node2
docker run -d -p 22184:2181 -p 22185:2888 -p 22186:3888 --name zookeeper_node2 --restart always -v /appdata/docker/zookeeper/node2/volume/data:/data -v /appdata/docker/zookeeper/node2/volume/datalog:/datalog -e "TZ=Asia/Shanghai" -e "ZOO_MY_ID=2" -e "ZOO_SERVERS=server.1=172.16.82.128:22182:22183 server.2=0.0.0.0:2888:3888 server.3=172.16.82.128:22188:22189" zookeeper

# node3
docker run -d -p 22187:2181 -p 22188:2888 -p 22189:3888 --name zookeeper_node3 --restart always -v /appdata/docker/zookeeper/node3/volume/data:/data -v /appdata/docker/zookeeper/node3/volume/datalog:/datalog -e "TZ=Asia/Shanghai" -e "ZOO_MY_ID=3" -e "ZOO_SERVERS=server.1=172.16.82.128:22182:22183 server.2=172.16.82.128:22185:22186 server.3=0.0.0.0:2888:3888" zookeeper
```

