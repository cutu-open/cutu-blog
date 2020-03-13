---
title: "Syntax"
date: 2020-02-09T23:09:06+08:00
draft: false
authorEmoji: 🤖 # emoji for subtitle, summary meta data
authorImage: "/img/whoami/avatar1.jpg" # image path in the static folder
authorDesc: "hello"# author description
tags: ["tutorial","MongoDB"]
categories: ["MongoDB"]
series: ["Tutorial"]
description: "MongoDB语法"
title: "MongoDB语法"
---
# 一、语法
## 1、查询

## 2、修改
```
db.some_collection.update(
    <query>,
    <update>,
    <options>
)
```

## 3、删除

## 4、添加
```
db.some_collection.insert([document])
```

## 5、其它
```mongodb
show dbs;

use some_db;

// 查询当前数据库
db;

// 删除数据库
some_db.dropDatabase();

// 创建集合
db.createCollection(name, options)

// 删除集合
db.some_collection.drop()


```

# 与SQL的术语区别

|SQL术语|MongoDB术语|说明|
|:-|:-|:-|
|database|database|数据库|
|table|collection|表/集合|
|row|document|数据行/文档|
|column|field|字段/域|
|index|index|索引|
|table join|||
|primary key|primary key|主键|
