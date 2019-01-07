---
layout:     post
title:      tushare依赖的python包
subtitle:   tushare依赖的python包
date:       2019-01-07
author:     LZP
header-img: img/bg-it3.jpg
catalog: true
tags:
    - tushare
    - python包
---


### pyzmq
- Pyzmq是zeromq的Python绑定。zeromq是一个消息内核，从网络通信的角度看，它处于会话层之上，应用层之下，有了它，你甚至不需要自己写一行的socket函数调用就能完成复杂的网络通信工作。Pyzmq >= 2.2.0完全支持3.x和4.x的libzmq，但不支持PyPy上的libzmq 2。
- Pyzmq详细API文档：http://zeromq.github.io/pyzmq/
- 如果你对zeromq感兴趣，有一个很好的指南
- github主页：https://github.com/zeromq/pyzmq

### simplejson
- simplejson is a simple, fast, complete, correct and extensible JSON <http://json.org> encoder and decoder for Python 2.5+ and Python 3.3+. It is pure Python code with no dependencies, but includes an optional C extension for a serious speed boost.

### lxml
- lxml是python的一个解析库，支持HTML和XML的解析，支持XPath解析方式，而且解析效率非常高

- Python 标准库中自带了 xml 模块，但是性能不够好，而且缺乏一些人性化的 API，相比之下，第三方库 lxml 是用 Cython 实现的，而且增加了很多实用的功能，可谓爬虫处理网页数据的一件利器。lxml 大部分功能都存在 lxml.etree中

- XPath，全称XML Path Language，即XML路径语言，它是一门在XML文档中查找信息的语言，它最初是用来搜寻XML文档的，但是它同样适用于HTML文档的搜索

- XPath的选择功能十分强大，它提供了非常简明的路径选择表达式，另外，它还提供了超过100个内建函数，用于字符串、数值、时间的匹配以及节点、序列的处理等，几乎所有我们想要定位的节点，都可以用XPath来选择

- XPath于1999年11月16日成为W3C标准，它被设计为供XSLT、XPointer以及其他XML解析软件使用，更多的文档可以访问其官方网站：https://www.w3.org/TR/xpath/

### six
- Six is a Python 2 and 3 compatibility library

- Six没有托管在Github上，而是托管在了Bitbucket上，不过这些都不是重点，重点是它的作用。

- 众所周知 Python 2 和 Python 3 版本的分裂给 Python 开发者们带来了很大的烦恼，为了使代码同时兼容两个版本，往往要增加大量的代码。 于是 Six 出现了。正如它的介绍所说，它是一个专门用来兼容 Python 2 和 Python 3 的库。它解决了诸如 urllib 的部分方法不兼容， str 和 bytes 类型不兼容等“知名”问题。

- 它的效果怎么样？pypi上单日十万以上，单月几百万的下载量足以说明了。要知道诸如 Flask 和 Django 这类知名的库，月下载量也只有几十万。

### python-dateutil
- The dateutil module provides powerful extensions to the standard datetime module, available in Python.

### numpy
- NumPy is the fundamental package for scientific computing with Python.
- NumPy(Numerical Python) 是 Python 语言的一个扩展程序库，支持大量的维度数组与矩阵运算，此外也针对数组运算提供大量的数学函数库。

- NumPy 的前身 Numeric 最早是由 Jim Hugunin 与其它协作者共同开发，2005 年，Travis Oliphant 在 Numeric 中结合了另一个同性质的程序库 Numarray 的特色，并加入了其它扩展而开发了 NumPy。NumPy 为开放源代码并且由许多协作者共同维护开发。

- NumPy 是一个运行速度非常快的数学库，主要用于数组计算，包含：
 + 一个强大的N维数组对象 ndarray
 + 广播功能函数
 + 整合 C/C++/Fortran 代码的工具
 + 线性代数、傅里叶变换、随机数生成等功能

### pytz
- pytz brings the Olson tz database into Python. This library allows accurate and cross platform timezone calculations using Python 2.4 or higher. It also solves the issue of ambiguous times at the end of daylight saving time, which you can read more about in the Python Library Reference

### pandas
- pandas is an open source, BSD-licensed library providing high-performance, easy-to-use data structures and data analysis tools for the Python programming language.

- pandas 是基于NumPy 的一种工具，该工具是为了解决数据分析任务而创建的。Pandas 纳入了大量库和一些标准的数据模型，提供了高效地操作大型数据集所需的工具。pandas提供了大量能使我们快速便捷地处理数据的函数和方法。你很快就会发现，它是使Python成为强大而高效的数据分析环境的重要因素之一。

### idna
- A library to support the Internationalised Domain Names in Applications (IDNA) protocol as specified in RFC 5891. This version of the protocol is often referred to as “IDNA2008” and can produce different results from the earlier standard from 2003.

### chardet
- Chardet: The Universal Character Encoding Detector

- 字符串编码一直是令人非常头疼的问题，尤其是我们在处理一些不规范的第三方网页的时候。虽然Python提供了Unicode表示的str和bytes两种数据类型，并且可以通过encode()和decode()方法转换，但是，在不知道编码的情况下，对bytes做decode()不好做。

- 对于未知编码的bytes，要把它转换成str，需要先“猜测”编码。猜测的方式是先收集各种编码的特征字符，根据特征字符判断，就能有很大概率“猜对”。

- 当然，我们肯定不能从头自己写这个检测编码的功能，这样做费时费力。chardet这个第三方库正好就派上了用场。用它来检测编码，简单易用。

### certifi
- Certifi is a carefully curated collection of Root Certificates for validating the trustworthiness of SSL certificates while verifying the identity of TLS hosts. It has been extracted from the Requests project.

### urllib3
- urllib3 is a powerful, sanity-friendly HTTP client for Python. Much of the Python ecosystem already uses urllib3 and you should too. urllib3 brings many critical features that are missing from the Python standard libraries:
 + Thread safety.
 + Connection pooling.
 + Client-side SSL/TLS verification.
 + File uploads with multipart encoding.
 + Helpers for retrying requests and dealing with HTTP redirects.
 + Support for gzip and deflate encoding.
 + Proxy support for HTTP and SOCKS.
 + 100% test coverage.

- Urllib3是一个功能强大，条理清晰，用于HTTP客户端的Python库，许多Python的原生系统已经开始使用urllib3。Urllib3提供了很多python标准库里所没有的重要特性：

 1.线程安全
 2.连接池
 3.客户端SSL/TLS验证
 4.文件分部编码上传
 5.协助处理重复请求和HTTP重定位
 6.支持压缩编码
 7.支持HTTP和SOCKS代理

### requests

- Requests allows you to send organic, grass-fed HTTP/1.1 requests, without the need for manual labor. There's no need to manually add query strings to your URLs, or to form-encode your POST data. Keep-alive and HTTP connection pooling are 100% automatic, thanks to urllib3.

- Requests库是用Python编写的，基于urllib，采用Apache2 Licensed开源协议的HTTP库；

- 相比urllib库，Requests库更加方便，可以节约我们大量的工作，完全满足HTTP测试需求；

### msgpack
- msgpack是一个基于二进制高效的对象序列化Library用于跨语言通信。它可以像JSON那样,在许多种语言之间交换结构对象;但是它比JSON更快速也更轻巧。
- msgpack用起来像json，但是却比json快，并且序列化以后的数据长度更小，言外之意，使用msgpack不仅序列化和反序列化的速度快，数据传输量也比json格式小，msgpack同样支持多种语言。

### tushare
- Tushare是一个免费、开源的python财经数据接口包。

- 主要实现对股票等金融数据从数据采集、清洗加工 到 数据存储的过程，能够为金融分析人员提供快速、整洁、和多样的便于分析的数据，为他们在数据获取方面极大地减轻工作量，使他们更加专注于策略和模型的研究与实现上。

- 考虑到Python pandas包在金融量化分析中体现出的优势，Tushare返回的绝大部分的数据格式都是pandas DataFrame类型，非常便于用pandas/NumPy/Matplotlib进行数据分析和可视化。

- 当然，如果您习惯了用Excel或者关系型数据库做分析，您也可以通过Tushare的数据存储功能，将数据全部保存到本地后进行分析。