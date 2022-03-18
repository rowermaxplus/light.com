---
title: "博客集成GoogleAnalytics"
date: 2022-02-27
draft: false
aliases: [
    "/zh-cn/blog/blog/blog-GoogleAnalytics/"
]

keywords: ["博客", "GoogleAnalytics"]
description: "本文介绍了如何在博客上集成GoogleAnalytics"
series: ["自我提升"]
isCJKLanguage: true
---





这里两种方式：第一种直接修改主题，第二个在主题外面的layouts做出同样的修改

### 注册

注册https://analytics.google.com/，获得自己的googleAnalyticsID，登录https://analytics.google.com/

在管理网站页面可以查看，G-4xxxxxx



![image-20220227153144162](/self/blog/image-20220227153144162.png)



### 配置

在config.toml

[params]下

添加



```shell
googleAnalyticsID = "G-00000XXXXX"
```

在主题文件夹创建

layouts/partials/analytics-gtag.html

内容

```js
<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id={{ .Site.Params.GoogleAnalyticsID }}"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());

  gtag('config', '{{ .Site.Params.GoogleAnalyticsID }}');
</script>
```

在主题layouts/_default/baseof.html

head标签里面添加内容

```go
{{ if and (hugo.IsProduction) (.Site.Params.googleAnalyticsID) }}
  {{ partial "analytics-gtag.html" . }}
  {{ end }}
```



推送到github,然后访问下自己的网站，查看

![image-20220227153718116](/self/blog/image-20220227153718116.png)



参考链接：

https://gist.github.com/zjeaton/42246742cdaf2fb46400d04c2eba9a8a

https://froglegs.co/blog/code/2020/11/google-analytics-4/
