---
layout: post
title: Hexo搭建博客 - nexmoe主题
date: 2021-09-25
updated: 2021-09-25
categories: 网页服务器
description: Hexo搭建博客 - nexmoe主题
tags:
  - 网页服务器
  - 博客主题
  - 静态网页
---

因为自己对Volantis主题设置过于复杂，反而丢弃了博客的本意，就是多记录遇到的问题。所以改为用简单的noxmoe.
  
<!--more-->
noxmoe的文档写的感觉反而更容易让小白理解。

## Hexo前安装 
### 1.1 安装Node.js for Windows
下载地址：<https://nodejs.org> 或  
[中国淘宝镜像node.js](https://npm.taobao.org/mirrors/node)


### 1.2 安装Git for Windows
Windows：下载并安装 [git](https://git-scm.com/download/win) 
[中国淘宝镜像Git](https://npm.taobao.org/mirrors/git-for-windows/)  

## 安装Hexo
首先新建一个文件夹用于放这个Hexo博客，在文件夹内右键Git Bash Here即可直接到该文件夹。
![20210516072957.png](https://s.pc.qq.com/tousu/img/20210516/7862367_1621121512.jpg)
或者通过cd的方式切换到这个文件夹。
> d:\example

[Hexo官网](https://hexo.io/zh-cn/docs/)

```
npm install -g hexo-cli
```

然后

```
hexo init exampleblog
cd exampleblog
npm install
```
博客位置：d:\example\exampleblog  


## 配置主题nexmoe

在 blog/_config.yml 文件中找到并修改： 
> theme: nexmoe

在Git Bash终端输入:
```
npm i hexo-theme-nexmoe
```

基础配置已完成

## 安装WordCount
```
npm i --save hexo-wordcount
```

## 启用 Nexmoe
在 config.yml 中，修改 theme 的值为 nexmoe

## 配置 Nexmoe
安装好主题后，在 Hexo 根目录下修改 _config.nexmoe.yml
基础配置已完成


## 添加文件归档等
文件归档、友情链接等：
```
.
├── _config.nexmoe.yml
├── _config.yml
├── package.json
├── scaffolds
├── source
|   ├── _posts
|   ├── images
|   ├── about.md
|   ├── archives.md
|   └── friends.md 
└── themes
```
只需要在source文件夹下新建archives.md即可

里面内容示例如下
```
---
title: 文章归档
layout: archives
---
```


## 添加图片文件夹

hexo的全局assets就是source/images

例如
```
![ImageName](/images/2020/example.png)  
```


## 启用文章目录
在_config.nexmoe文件修改为true。
```
function: # 功能开关，可选值（true,false）
  globalToc: true # 开启该功能会自动开启文章 TOC（文章目录） 功能
```




## 本地运行Hexo
```
hexo s --debug #直接本地运行此命令即可

# ===================
hexo g
# hexo g = hexo generate #生成html

hexo s
#hexo s = hexo server #启动服务预览

hexo clean
#清除缓存html
```