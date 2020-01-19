---
title: "Hugo"
date: 2020-01-19T14:43:26+08:00
draft: false
---
# Hugo指南

## 文件结构
### Archetypes
`hugo new` 创建post时的模板文件位置。如果没有文件，则去主题中查找
- 例子
```sh
hugo new posts/my-first-post.md
```
上面的命令会创建一个文件 `content/posts/my-first-post.md` ，使用的模板为以下地址中检索到的第一个
1. `archetypes/posts.md`
2. `archetypes/default.md`
3. `themes/my-theme/archetypes/posts.md`
4. `themes/my-theme/archetypes/default.md`




```sh
hugo server
```

