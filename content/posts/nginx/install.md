---
title: "Install"
date: 2020-02-08T22:08:00+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","Nginx"]
categories: ["Nginx"]
series: ["Tutorial"]
description: "安装Nginx"
title: "Nginx-安装"
---
# Linux
## 自定义编译安装
### 一、Centos
1. 安装依赖
```bash
yum -y install gcc zlib zlib-devel pcre-devel openssl openssl-devel
```
2. 下载nginx安装包
```bash
wget http://nginx.org/download/nginx-1.17.8.tar.gz
```
3. 解压安装压缩包
```bash
tar -xvf nginx-1.17.8.tar.gz
```
4. 配置
```bash
./configure \
   --with-openssl=../openssl-1.0.2s \
   --with-pcre=../pcre-8.43 \
   --with-zlib=../zlib-1.2.11 \
   --with-pcre-jit --user=admin \
   --prefix=/home/admin/nginx \
   --with-http_ssl_module \
   --with-http_v2_module 
```
> 参数说明

| 参数 | 描述 |
|:-|:-|
| `--prefix` |Nginx安装目录，以及有其他配置脚本选项的路径设置的所有相对路径的基本位置。默认值`/usr/local/nginx`|
|`--sbin-path`|Nginx二进制执行文件的名称，默认值:`<prefix>/sbin/nginx`|
|`--conf-path`|Nginx配置文件的名称。但是，您可以通过在nginx命令行上使用选项指定其他文件来始终在启动时覆盖此值。默认值：`<prefix> conf / nginx.conf-c <FILENAME>`|
|`--pid-path`|nginx.pid文件的名称，用于存储nginx主进程的进程ID 。安装后，可以使用Nginx配置文件中的pid指令更改文件名的路径。默认值：`<prefix> /logs/nginx.pid`|
|`--error-log-path`|error，warn和诊断数据的日志文件的名称。安装后，可以使用Nginx配置文件中的error_log指令更改文件名。默认值：`<prefix> /logs/error.log`|
|`--http-log-path`|HTTP服务器请求的主日志文件的名称。安装后，始终可以使用Nginx配置文件中的access_log指令更改文件名。默认值:`<prefix> /logs/access.log`|
|`--user`|Nginx运行进程的拥有者。安装后，可以使用Nginx配置文件中的user指令更改名称。默认：nobody|
|`--group`|nginx运行进程的拥有者用户组。安装后，可以使用NGINX配置文件中的user指令更改名称。默认值：--user选项设置的值|
|`--with-pcre`|PCRE库源代码的路径，这是位置指令和Rewrite模块中正则表达式支持所必需的|
|`--with-pcre-jit`|使用“即时编译”支持（pcre_jit指令）构建PCRE库|
|`--with-zlib`|zlib库的源代码路径，Gzip模块需要该路径|
|`--with-http_ssl_modul`|启用HTTPS支持|
|`--with-http_v2_module`|开启 HTTP/2请求支持|
|||

5. 编译
```bash
make
```

6. 安装
```bash
make install
```

7. 分配权限（Optinal）
```bash
sudo chown root nginx
sudo chmod u+s nginx
```

### 二、Debian（Ubuntu、Deepin）
1. 安装依赖
```bash
sudo apt-get -y gcc zlib zlib-devel pcre-devel openssl openssl-devel
```
> 同CentOS

