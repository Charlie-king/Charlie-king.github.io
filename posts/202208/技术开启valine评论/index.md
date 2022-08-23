# hugo博客开启valine评论系统配置


<!--more-->

{{< admonition tip "valine评论设置" >}}
用hugo搭建的博客，采用fixIt主题（魔改于loveit），支持多种评论系统设置。valine评论是搭配LeanCloud平台来一起使用的。
{{< /admonition >}}


### [valine](https://valine.js.org/)特性

-   快速
-   安全
-   Emoji 😉
-   无后端实现
-   MarkDown 全语法支持
-   轻量易用
-   [文章阅读量统计](https://valine.js.org/visitor.html) `v1.2.0+`

### LeanCloud介绍
LeanCloud（原 AVOS Cloud） 是针对移动应用的一站式云端服务，专注于为应用开发者提供工具和平台。提供包括**LeanStorage 数据存储、LeanMessage 通信服务、LeanAnalytics 统计分析、LeanModules 拓展模块**等四大类型的后端云服务，加速应用开发。

这里以valine为例讲解一下如何配置，其余博客诸如hexo等，都是大同小异。

**主要步骤分为两步：**

1.  leancloud注册获取ID和key
2. `config.toml`配置文件配置参数 


### leancloud获取APP ID ，APP Key，服务器地址
1. **注册leancloud**，国际版和国内版（华东区/华北区）可选，账户不互通的，国际版不需要实名，绑定域名也不需要备案。建议选国际版。
2. 创建一个应用，`开发版`够用，名称随意。
![](https://s3.bmp.ovh/imgs/2022/08/23/3c7ae83b11964f52.png)

3. 在`设置` > `应用`中可查看到 APP ID，APP Key和服务器地址。

> 注意：服务器地址这里是默认leancloud提供的域名，但是从2022年8月1号开始，这个域名国内不能直接访问了，因此需要绑定自定义api域名。我刚好遇到这个坑，原来用的是默认的域名，后面突然发现不能评论，一通操作才发现这个问题。

![](https://s3.bmp.ovh/imgs/2022/08/23/3f85839cd5f21b2d.png)

4. **绑定域名**

	这里只开通评论的话，接3步骤绑定api域名即可，然后去域名管理中心添加一条cname指向它这里的域名，添加好后会显示部署证书，十几分钟后生效，提示已绑定。

	再去**应用凭证**那里可以看到服务器地址更新为你刚绑定的api域名。

![](https://s3.bmp.ovh/imgs/2022/08/23/2e9ebace344ddb15.png)


5. **填写安全域名**
填写`应用` > `设置` > `安全设置`中的 Web 安全域名。把你的博客域名添加上去。

由于 App ID 和 App Key 是完全暴露的，任何人都可以访问我们的资源。为了防止他人使用，我们需要配置 Web 安全域名，只有添加的域名才可以使用资源。
![](https://s3.bmp.ovh/imgs/2022/08/23/6d6eff52af936782.png)

### `config.toml`配置

将上面步骤获得的APP ID，APP Key和服务器地址填入以下对应的参数位置。

~~~toml
#以下配置为 loveit，fixIt主题下的config配置

[params.page.comment.valine]

appId = "填写leancloud里的APP ID"  #参看上面步骤

appKey = "填写leancloud里的APP Key"  #参看上面步骤

avatar = "monsterid" #评论者gravatar头像，参看全球头像那篇文章

enable = true

enableQQ = true  

highlight = true

lang = "zh-CN"  

meta = ['nick', 'mail', 'link']  #评论昵称，邮件，链接三个模块

pageSize = 10 

placeholder = "欢迎交流！匿名昵称留空即可，已开启邮箱留言自动通知提醒。" #评论区提醒文字

recordIP = true  #是否记录ip

serverURLs = "填写leancloud里的服务器地址"  #参看上面步骤

visitor = false  #是否开启访问量统计

#  emoji 数据文件名称，默认是 "google.yml"

# ("apple.yml", "google.yml", "facebook.yml", "twitter.yml")

# 位于 "themes/FixIt/assets/data/emoji/" 目录

# 可以在你的项目下相同路径存放你自己的数据文件：

# "assets/data/emoji/"

commentCount = true #评论统计

emoji = ""  # emoji表情


~~~


配置后

记得在文章的前置参数里把`comment`改为true。
``` toml
title: "valine评论系统配置"
subtitle: ""
date: 2022-08-22T11:15:06+08:00

author: "Kingpo"
authorLink: ""
authorEmail: ""
description: ""
keywords: ""
comment: true  #评论开启
weight: 0
```


运行效果如下：
![](https://s3.bmp.ovh/imgs/2022/08/23/fca811ded03ff90f.png)


至此，评论功能已经开启。

可以进行评论了，这里没做限制，任何人均可留言，昵称或邮箱，网址留或不留均可。

valine无后端，那么评论的数据在哪里管理呢。

答案是在leancloud平台上，评论数据都会存储在名为 `Comment` 的 Class 中，需要自行登陆 `LeanCloud 应用` 管理。

进入你的`应用` > `存储` > `Comment`，之后你可以对所有评论进行操作。
![](https://s3.bmp.ovh/imgs/2022/08/23/4f0de8a3925b9f55.png)


**如果想要评论数据后端管理，并开启实时邮件通知，参看我这篇**[valine评论设置邮件通知和valine-admin后台管理](/posts/202208/技术valine评论设置邮件通知和valine-admin后台管理/)
