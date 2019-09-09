---
title: GitHub命令行之克隆线上仓库和上传本地文件
date: 2019-08-22 16:18:50
categories: 命令行
tags: GitHub
---
`GitHub`是用于版本控制和协作的代码托管平台。它可以让您和其他人在任何地方协同工作。
### 克隆线上仓库
1. 在网页版GitHub上创建远程仓库
2. 在磁盘上创建本地仓库文件夹
3. 在本地仓库文件夹打开`cmd操作界面`进行命令行操作，把GitHub的线上仓库克隆到本地
``` bash
$ git clone https://github.com/ShawLive/vueDemo.git 
注：https://github.com/ShawLive/vueDemo.git 表示我GitHub的线上仓库路径
```

### 上传本地文件
1. 把要上传的文件拖拽到已克隆好的本地仓库中
2. 查看准备提交的文件状态
``` bash
$ git status 
```
3. 探测本地仓库的新增、修改、删除
``` bash
$ git add . 
注：add空格后面有一点（ . ）
```
4. 对你提交的内容进行描述
``` bash
$ git commit -m "readme" 
注：双引号里填写的是你对提交的内容进行描述
```
5. 上传文件
``` bash
$ git push 
注：已配置GitHub的用户名和邮箱，可直接上传文件
$ git push -u origin master  
注：未配置GitHub的用户名和邮箱，此处需要你配置一下
```
