---
title: "修改typora字体"
date: 2022-03-18
draft: false
aliases: [
    "/zh-cn/blog/blog-typora/"
]
keywords: ["typora", "字体", "font"]
description: "本文介绍了如何修改typora的字体"
series: ["自我提升"]
isCJKLanguage: true
---









### 下载字体

------

楼主下载的一款字体

[霞鹜文楷](https://github.com/lxgw/LxgwWenKai/releases)



下载到本地，解压缩后，几个ttf文件，右键点击安装即可。安装后可以打开一个word文档，在字体中查找下载的字体。



### 修改typora字体

------

找到对应的theme文件夹，对应的主题的css文件。

这里我以drake的主题为例，drake主题将变量定义在了一个全局变量里面。可以看到它text-font对应的是--monospace，所以我们只要在--monospace里面添加字体就行了。测试了下，应该是不带引号的对应的是英文字体，带引号的对应的是中文字体，所以把中文字体加上就行了。





![image-03](/self/blog/image-03.png)



最后重启typora就行了。



### 参考链接

------

[把typora改为微软雅黑+Consolas](https://www.cnblogs.com/asheng2016/p/8979282.html)

