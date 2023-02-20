---
layout: post
title: Hexo搭建博客 - nexmoe主题
date: 2021-09-25
updated: 2023-02-02
categories: 网页服务器
description: Hexo搭建博客 - nexmoe主题
tags:
  - 网页服务器
  - 博客主题
  - 静态网页
---

因为自己对Volantis主题设置过于复杂，反而丢弃了博客的本意，就是多记录遇到的问题。所以改为用简单的noxmoe.

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
或者通过cd的方式切换到这个文件夹。
> d:\example

[Hexo官网](https://hexo.io/zh-cn/docs/)

```
npm install -g hexo-cli
```

然后

```
npx hexo init exampleblog
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
由于nexmoe v4版本评论功能配置对新手非常不好，这里建议锁定更新版本为v3最后一版：

```
npm i hexo-theme-nexmoe@3.2.13
```

基础配置已完成

## 安装WordCount
```
npm i --save hexo-wordcount
```

## 安装本地搜索功能
nexmoe主题可以使用Bing也可以使用本地搜索，经过测试后发现Bing几乎搜索不出来。建议直接使用本地搜索。
```
npm i -S hexo-generator-json-content
```
之后在_config.nexmoe.yml里将enable改为true，而type为local即可：
```
widgets:
    - name: search
      enable: true
      options: 
        search: 
            type: local
```


  
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
## 修改icon
普通小icon来源iconfont，没有找到预览方式。不过可以进去文件夹找到svg后猜测  

```
node_modules\hexo-theme-nexmoe\source\lib\iconfont\iconfont.svg
#或者直接看css 更快
```
  
例如：
```
<glyph glyph-name="douban-fill" ... .../>
```
就可以猜测是icon-douban-fill。


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

## 启用部分文章加密
[Hexo-blog-encrypt](https://github.com/D0n9X1n/hexo-blog-encrypt)  
运行
```
npm install --save hexo-blog-encrypt
```

然后在文章中加入password即可
```
---
title: Hello World
date: 2016-03-30 21:18:02
password: hello
---
```

## 评论功能
需要将node_modules文件夹内的hexo-theme-nexmoe复制到项目文件夹\themes下。
将themes\nexmoe\layout\_comment\waline.ejs以及_config.nexmoe.yml文件修改。
可以参考valine的设置。

## 本地运行Hexo命令及主题升级
本地运行hexo请到[Hexo基础命令](/2021/09/26/2021-09-26-Hexo-Update-Theme-Update)查看。