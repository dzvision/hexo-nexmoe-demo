---
layout: post
title: Hexo基础命令以及升级以及Hexo的主题升级方式
date: 2021-09-26
updated: 2021-09-26
categories: 网页服务器
description: Hexo基础命令升级以及Hexo的主题升级
tags:
  - 网页服务器
  - 博客主题
  - 静态网页
---

Hexo升级以及Hexo的主题升级方式


<!--more-->

## 本地运行Hexo
```
npx hexo s --debug #直接本地运行此命令即可

# ===================
npx hexo g
# hexo g = hexo generate #生成html

npx hexo s
#hexo s = hexo server #启动服务预览

npx hexo clean
#清除缓存html
```



## 升级Node.js
### 1.1 安装Node.js for Windows
Hexo升级前请先确认NodeJS版本并升级。  

```
node -v #查看版本
```
  
下载地址：<https://nodejs.org> 或  
[中国淘宝镜像node.js](https://npm.taobao.org/mirrors/node)

直接下载最新版替换即可



## 本地运行Hexo
```
npx hexo g
# hexo g = hexo generate #生成html

npx hexo s
#hexo s = hexo server #启动服务预览

npx hexo clean
#清除缓存html
```

## 升级Hexo和主题

```
npx hexo -v 
# 查看 hexo及组件依赖等版本

PS A:\hexo-vlts> npx hexo -v
INFO  Validating config
hexo: 5.4.2
hexo-cli: 4.3.0
os: win32 10.0.19044
node: 18.13.0
v8: 10.2.154.23-node.21
uv: 1.44.2
zlib: 1.2.13
brotli: 1.0.9
ares: 1.18.1
nghttp2: 1.51.0
napi: 8
llhttp: 6.0.10
uvwasi: 0.0.13
openssl: 3.0.7+quic
cldr: 42.0
icu: 72.1
tz: 2022f
unicode: 15.0
ngtcp2: 0.8.1
nghttp3: 0.7.0

```

去到文件夹下package.json, 并将hexo版本修改为新版本：
例如原本：
```
{
  "name": "hexo-site",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "build": "hexo generate",
    "clean": "hexo clean",
    "deploy": "hexo deploy",
    "server": "hexo server"
  },
  "hexo": {
    "version": "5.2.0"
  },
  "dependencies": {
    "hexo": "^4.3.0",
    "hexo-blog-encrypt": "^3.1.6",
    "hexo-generator-archive": "^2.0.0",
    "hexo-generator-category": "^1.0.0",
    "hexo-generator-index": "^2.0.0",
    "hexo-generator-tag": "^1.0.0",
    "hexo-renderer-ejs": "^2.0.0",
    "hexo-renderer-marked": "^4.0.0",
    "hexo-renderer-stylus": "^2.1.0",
    "hexo-server": "^3.0.0",
    "hexo-theme-landscape": "^0.0.3",
    "hexo-theme-volantis": "^4.0.1",
    "hexo-wordcount": "^6.0.1"
  }
}
```

例如将依赖内的hexo版本修改为^5.3.0(高于5.3.0)版本   
```
  "dependencies": {
    "hexo": "^5.3.0",
  }
```    
那么在npm update之后，他会安装较新版本。之后你可以再次修改package.json文件直接将hexo和依赖修改为确定的新版本的数字。
同理，想要升级hexo主题，也只是将依赖内主题的版本号，直接改高，或者改为*。再用hexo -v确定版本后可以再修改为数字版本。

如果升级后发现兼容问题可以直接废弃这个项目，使用全新安装的方式重新部署。