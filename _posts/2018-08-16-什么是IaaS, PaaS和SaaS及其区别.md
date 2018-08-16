---
layout:     post
title:      轻轻松松理解IaaS, PaaS和SaaS
subtitle:  什么是IaaS, PaaS和SaaS及其区别
date:       2018-08-16
author:     LZP
header-img: img/bg-it1.jpg
catalog: true
tags:
    - IaaS
    - PaaS
    - SaaS
---

> 云服务只是一个统称，可以分成三大类。
> ![](http://www.ruanyifeng.com/blogimg/asset/2017/bg2017072301.jpg)

```

IaaS：基础设施服务，Infrastructure-as-a-service
PaaS：平台服务，Platform-as-a-service
SaaS：软件服务，Software-as-a-service

```

## IaaS: Infrastructure-as-a-Service（基础设施即服务）

> 第一层叫做IaaS，有时候也叫做Hardware-as-a-Service，几年前如果你想在办公室或者公司的网站上运行一些企业应用，你需要去买服务器，或者别的高昂的硬件来控制本地应用，让你的业务运行起来。

但是现在有IaaS，你可以将硬件外包到别的地方去。IaaS公司会提供场外服务器，存储和网络硬件，你可以租用。节省了维护成本和办公场地，公司可以在任何时候利用这些硬件来运行其应用。

一些大的IaaS公司包括Amazon, Microsoft, VMWare, Rackspace和Red Hat.不过这些公司又都有自己的专长，比如Amazon和微软给你提供的不只是IaaS，他们还会将其计算能力出租给你来host你的网站。

IaaS 是云服务的最底层，主要提供一些基础资源。它与 PaaS 的区别是，用户需要自己控制底层，实现基础设施的使用逻辑。下面这些都属于 IaaS。
>
> * Amazon EC2
> * Digital Ocean
> * RackSpace Cloud

## PaaS: Platform-as-a-Service（平台即服务）

> 第二层就是所谓的PaaS，某些时候也叫做中间件。你公司所有的开发都可以在这一层进行，节省了时间和资源。

PaaS公司在网上提供各种开发和分发应用的解决方案，比如虚拟服务器和操作系统。这节省了你在硬件上的费用，也让分散的工作室之间的合作变得更加容易。网页应用管理，应用设计，应用虚拟主机，存储，安全以及应用开发协作工具等。

一些大的PaaS提供者有Google App Engine,Microsoft Azure，Force.com,Heroku，Engine Yard。最近兴起的公司有AppFog, Mendix 和 Standing Cloud

PaaS 提供软件部署平台（runtime），抽象掉了硬件和操作系统细节，可以无缝地扩展（scaling）。开发者只需要关注自己的业务逻辑，不需要关注底层。下面这些都属于 PaaS。
>
> * Heroku
> * Google App Engine
> * OpenShift

## SaaS: Software-as-a-Service（软件即服务）

> 第三层也就是所谓SaaS。这一层是和你的生活每天接触的一层，大多是通过网页浏览器来接入。任何一个远程服务器上的应用都可以通过网络来运行，就是SaaS了。

你消费的服务完全是从网页如Netflix, MOG, Google Apps, Box.net, Dropbox或者苹果的iCloud那里进入这些分类。尽管这些网页服务是用作商务和娱乐或者两者都有，但这也算是云技术的一部分。

一些用作商务的SaaS应用包括Citrix的GoToMeeting，Cisco的WebEx，Salesforce的CRM，ADP，Workday和SuccessFactors。

![](https://gss0.baidu.com/-4o3dSag_xI4khGko9WTAnF6hhy/zhidao/wh%3D600%2C800/sign=9fb0878813ce36d3a2518b360ac316bf/86d6277f9e2f0708ec3d5152ef24b899a901f2ac.jpg)

SaaS 是软件的开发、管理、部署都交给第三方，不需要关心技术问题，可以拿来即用。普通用户接触到的互联网服务，几乎都是 SaaS，下面是一些例子。
>
> * 客户管理服务 Salesforce
> * 团队协同服务 Google Apps
> * 储存服务 Box
> * 储存服务 Dropbox
> * 社交服务 Facebook / Twitter / Instagram

对应软件开发，则是下面这张图。
![](http://www.ruanyifeng.com/blogimg/asset/2017/bg2017072307.jpg)
