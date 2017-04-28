---
title: 在githubpage 使用hexo
date: 2017-04-28 00:13:04
tags: hexo
---

## 本地依赖环境
在本地安装git、nodejs环境

## 配置hexo
1. 安装hexo
```shell
npm install -g hexo-cli
```

2. 初始化hexo项目
```shell
hexo init blog
cd blog
npm install
```
这样最简单的hexo本地环境就配好了

<!--more-->

## 下面是常用的hexo命令
- 创建新的博客
```
hexo new blog_name
```
- 生成静态页面
```shell
hexo g # 或者hexo generate 
```
- 在本地查看网页效果（在浏览器访问localhost:4000）
```shell
hexo s # 或者hexo server
```
- 生成静态页面并部署到GitHub
```shell
hexo generate -d
```

##  配置github
1. 设置github部署插件
```shell
npm install hexo-deployer-git --save
```
2. 修改_config.yml配置文件中的deploy部分
```shell
deploy:
  type: git
  repo: <repository url>
  branch: [branch]
  message: [message]
```

## 更换next主题
1. 下载next主题到themes文件夹下
```shell
git clone https://github.com/iissnan/hexo-theme-next themes/next
```
2. 修改_config.yml配置文件中的theme为next
```shell
theme: next
```

## 配置域名
在/blog/themes/next/source目录下新建文件名为：CNAME文件，注意没有后缀名！直接将自己的域名如：gonghonglou.com写入。

## 将项目部署到Coding上
1. 在Coding上创建项目
2. 配置_config.yml
```shell
deploy:
  type: git
  repository: 
            github: git@github.com:gonghonglou/gonghonglou.github.io.git
            coding: git@git.coding.net:gonghonglou/gonghonglou.git
  branch: master
```
3. cd 到本地 blog/source 目录下执行如下命令新建 Staticfile 文件，原因是 coding.net 需要以这个文件来作为静态文件部署的标志，就是说看到这个 Staticfile 就知道按照静态文件来发布。
4. 个人域名添加两条 CNAME 解析。将github.io. 解析为 [海外] ，将 coding.me. 解析为 [默认]
![](http://image.gonghonglou.com/firstblog/two-cname.png)
