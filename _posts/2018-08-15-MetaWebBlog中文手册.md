---
layout:     post
title:      MetaWeblog API中文手册
subtitle:   Blog开发实践之MetaWeblog
date:       2018-08-15
author:     LZP
header-img: img/bg-it1.jpg
catalog: true
tags:
    - MetaWeblog
    - Blog
---

## MetaWeblog API中文手册

### 1、什么是MetaWeblog？

MetaWebBlog API（MWA）是一个Blog程序接口标准，允许外部程序来获取或者设置Blog的文字和熟悉。他建立在XMLRPC接口之上，并且已经有了很多的实现。

### 2、基本的函数规范

> 有三个基本的函数规范：
>
> * metaWeblog.newPost (blogid, username, password, struct, publish) 返回一个字符串，可能是Blog的ID。
> * metaWeblog.editPost (postid, username, password, struct, publish) 返回一个Boolean值，代表是否修改成功。
> * metaWeblog.getPost (postid, username, password) 返回一个Struct。
>
>
> 函数参数解释
>
> * 其中blogid、username、password分别代表Blog的id（注释：如果你有两个Blog，blogid指定你需要编辑的blog）、用户名和密码。
> * struct的含意：
>   在newPost和editPost中，struct是一个RSS 2.0规范中里面的定义。的定义如下：
>
> 元素
> 说明
> 例子
>
>title
The title of the item.
Venice Film Festival Tries to Quit Sinking
>
>link
The URL of the item.
http://nytimes.com/2004/12/07FEST.html
>
>description
The item synopsis.
Some of the most heated chatter at the Venice Film Festival this week was about the way that the arrival of the stars at the Palazzo del Cinema was being staged.
>
>author
Email address of the author of the item
>
>category
Includes the item in one or more categories
>
>comments
URL of a page for comments relating to the item
>
>enclosure
Describes a media object that is attached to the item
>
>guid
A string that uniquely identifies the item.
>
>pubDate
Indicates when the item was published.
>
>source
The RSS channel that the item came from.
>
>其中最主要的三个元素是title、link和description。如果Blog工具不支持title和link，description就是目录（Content）。category是一个数组，是这个Post所属的类别。如果类别不存在，服务器端将只处理存在的类别。

### 3、metaWeblog.newMediaObject 
>metaWeblog.newMediaObject (blogid, username, password, struct) 返回一个数组
>
>其中blogid、username、password分别代表Blog的id（注释：如果你有两个Blog，blogid指定你需要编辑的blog）、用户名和密码。struct必须包含name, type 和bits三个元素，当然也可以包含其他元素。
>
>name代表数据的名称，type是数据的MIME类型，譬如audio/mpeg 、image/jpeg和video/quicktime。bits是数据的base64编码形式的数据流。
>
>如果调用失败，它显示错误信息。如果调用成功，返回值是一个Struct，里面至少包含一个Url元素，代表数据的HTTP或者FTP Url。

### 4、metaWeblog.getCategories

>metaWeblog.getCategories (blogid, username, password) 返回一个struct。
>
>返回值包含所有的Blog的类别，每一个列别包含description, htmlUrl and rssUrl。

### 5、metaWeblog.getRecentPosts

>metaWeblog.getRecentPosts (blogid, username, password, numberOfPosts) 返回一个结构（struct）的数组（array）。
>
>每一个Struct包含getPost返回值一样的结构。
>
>numberOfPosts是返回的数量。

### 6、调用验证和错误显示

>同Blogger API不同的是，metaWeblog没有APPKEY这个概念，你可以自己设置。
>
>同时建议使用标准的XMLRPC Fault来显示错误。

-----
* [博客园cnblogs.com支持的MetaWeblogAPI](http://rpc.cnblogs.com/metaweblog/cc11001100)
* http://www.xmlrpc.com/  最权威的站，介绍了什么是xml-rpc，规范，实现的语言，mail list
* http://www.xmlrpc.com/spec   英文的xml-rpc规范
* [RFC: MetaWeblog API:](http://www.xmlrpc.com/metaWeblogApi)   MetaWeblog API 规范
* http://www.duduwolf.com/post/41.asp  中文翻译的xml-rpc规范（感谢翻译者：滴水）
* http://www.XML-RPC.Net XML-RPC的.NET 实现,其中有最新.net2.0的XML-RPC实现的下载
* [MetaWeblogAPI and MSN Spaces](http://msdn.microsoft.com/library/default.asp?url=/library/en-us/msnspaces/MetaWeblogAPI_Introduction.asp)  MSDN上关于MetaWeblog API及MSN Spaces接口的说明及.NET示例