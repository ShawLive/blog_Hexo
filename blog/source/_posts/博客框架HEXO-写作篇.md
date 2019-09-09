---
title: 博客框架HEXO-写作篇
date: 2019-08-22 17:07:06
categories: 命令行
tags: Hexo
---
`Hexo`是一个快速、简洁且高效的博客框架。`Hexo`使用`Markdown`（或其他渲染引擎）解析文章，在几秒内，即可利用靓丽的主题生成静态网页。
1. 创建博客目录
``` bash
$ hexo new [layout] <title>
注：在命令中指定文章的布局（layout），默认为 post。
```
2. 本地服务访问
``` bash
$ hexo clean		//清除缓存文件和已生成的静态文件
$ hexo g		//生成静态文件（生成网站页面）
$ hexo s		//启动本地服务（查看生成的网站）
注：浏览器上输入localhost:4000查看效果
```
3. 远程存储访问
``` bash
$ hexo clean		//清除缓存文件和已生成的静态文件
$ hexo g		//部署之前预先生成静态文件
$ hexo d		//文件生成后立即部署网站
注：如果打开本地服务，需停止服务才能继续输入命令（停止服务快捷键Ctrl+c）
```
