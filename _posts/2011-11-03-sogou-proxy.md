---
layout: post
title: "Linux下独立使用搜狗浏览器代理"
description: ""
category: tech
tags: [linux, wine, sogou, proxy, network]
---
{% include JB/setup %}

教育网实在是蛋疼，国外代理经常出问题，而且访问国内网站不够快，于是又想起用搜狗浏览器的代理了。Linux下面用wine安装，启动搜狗浏览器，然后Firefox挂代理上网。

嫌麻烦了，于是就想办法不启动搜狗浏览器。其实和windows下面单独使用搜狗浏览器代理原理类似，只能用旧的版本了 http://download.ie.sogou.com/sogouexplorer1.1beta.exe ，安装好后运行，启用加速，然后在终端里面执行ps aux |grep sogou ，可以看到这样的结果

所以我们就照着这个以后运行`wine sogouexplorer.exe -proxy at1.dll EDUANDVIDEO D5AA5E6CC265B9CC187E7523AAE5847E` 就可以了。后面的一串字符不这样也可以，但是就照着来吧，注意下sogouexplorer.exe和at1.dll的路径，默认在~/.wine /drive_c/Program\ Files/SogouExplorer 里面，浏览器设置http 127.0.0.1:8081的代理。如果不能启用加速功能，请检查dns设置，要使用教育网的dns才可以。

另外网上找到的一个用Python写的程序，额，很强大： [http://xiaoxia.org/2011/03/26/using-python-to-write-a-local-sogou-proxy-server-procedures/][xiaoxia] 这里默认的代理是http 127.0.0.1:1998 ，python的话windows, linux, mac各种平台都能用了。

[xiaoxia]: http://xiaoxia.org/2011/03/26/using-python-to-write-a-local-sogou-proxy-server-procedures/ 
