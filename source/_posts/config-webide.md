---
title: 配置webide
date: 2017-04-28 00:14:01
tags: hexo
---

为了在本地配置webide，花费了好久的时间下载yarn、 webpack和babel的依赖，结果配置好以后，依然无法正常访问
最终还是选择了用docker的形式。自行安装docker。然后执行如下命令就可以了。
```shell
docker run -p 8080:8080 --name webide webide/webide
```