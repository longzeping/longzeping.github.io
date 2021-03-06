---
layout:     post
title:      为Gitalk和Gitment初始化全部评论
subtitle:   用ruby和Github API初始化博客的全部评论
date:       2018-08-02
author:     LZP[原创]
header-img: img/bg-it8.jpg
catalog: true
tags:
    - ruby
    - github
    - Gitalk
---

## 为Gitalk和Gitment初始化全部评论

#### 这段ruby代码，自动根据网址，为Gitalk、Gitment初始化全部评论

```ruby

# InitCommentForGithubSite.rb
# 本程序用于初始化Gitalk或者Gitment的评论
# Gitalk和Gitment是Github Pages创建的博客的最佳评论插件，使用了Issues作为博客评论
# 使用本程序前，_config.yml配置文件必须加上下面这一句，用于生成sitemap.xml文件
#   plugins:
#    - jekyll-sitemap   #jekyll的站点地图插件，用于生成站点地图

# 需要初始化Gitalk评论的网址，以下四条需修改为自己的内容
site_url = "https://long***ing.github.io"  # 需修改为自己的网址
username = "long***ing" # GitHub 用户名，需修改为自己的用户名
token = "246c14c************aa621dcdfe6a5643acdf3"   # GitHub Token，在账户设置中申请
repo_name = "long***ing.github.io"  # 存放 issues，需修改为自己的仓库名

# Issue标签，Issue可以加很多个标签
label1 = "Gitalk"    # Issue的标签1，我用"Gitalk"标识这类issue是给Gitalk插件使用的

require 'open-uri'
require 'faraday'
require 'active_support'
require 'active_support/core_ext'
require 'sitemap-parser'

sitemap_url = "#{site_url}/sitemap.xml"    # sitemap
sitemap = SitemapParser.new sitemap_url
urls = sitemap.to_a

# 建立到指定用户名、指定指定仓库的issues的链接
conn = Faraday.new(:url => "https://api.github.com/repos/#{username}/#{repo_name}/issues") do |conn|
  conn.basic_auth(username, token)
  conn.adapter  Faraday.default_adapter
end

urls.each_with_index do |url, index|
    #url = URI::escape(url)  #url中可能含有中文，需要先编码

    #从url读取网页，并获取网页的标题（title），标题可能是中文，所以要使用UTF-8编码
    title = open(url).read.scan(/<title>(.*?)<\/title>/).first.first.force_encoding('UTF-8')

    # Issue的标签2，我用特定博文的url的pathname作标签，让issue和博文对应，注意要解码，否则会标签长度
    uri = URI(url)  
    label2 = URI::unescape(uri.path)    #用这句直接获取pathname

    # Issue的内容，内容为带链接的标题（Issue支持Markdown，使用Markdown语法）
    # issueBody = "![#{title}](#{url})"
    #上面用markdown语法，可以写进去，但访问时被跳转了，所以改为直接写url
    issueBody = "#{title} #{url}"

    # post一个json格式的数据给前面建立的连接，这个json格式的数据描述了一个issue
    response = conn.post do |req|
        req.body = { body: issueBody, labels: [label1, label2], title: title }.to_json
    end
    puts response.body
end


```

**把这段代码保存为文件 InitCommentForGithubSite.rb**

#### 执行这段代码即可

###### 命令行执行
>ruby InitCommentForGithubSite.rb

----

## 相关参考：
>[《Github Token的申请和使用》](https://longzeping.github.io/2018-08-01-Github-Token的申请和使用/)
>[《ruby和ruby库的安装》](https://longzeping.github.io/2018-08-01-ruby和ruby库的安装/)
>[《Jekyll自动生成站点地图》](https://longzeping.github.io/2018-08-01-Jekyll自动生成站点地图/)