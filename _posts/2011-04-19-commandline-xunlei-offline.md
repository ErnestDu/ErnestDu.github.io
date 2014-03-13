---
layout: post
title: "用命令行下载迅雷离线"
description: ""
category: tech
tags: [network, xunlei, linux]
---
{% include JB/setup %}

搞了个迅雷会员，离线下载和高速通道用起来还是很实用的。不过迅雷显然只能在Windows下面用了，在虚拟机里面还是感觉很卡。另外虽然用浏览器打开 [http://lixian.vip.xunlei.com][xunlei] 也可以下载，不过由于在教育网速度很慢，只能挂代理了。教育网ipv6代理速度快的时候能达到2~3M/s，但是最近总是不太稳定，导致浏览器下载经常出问题，常常没下载完就显示完成了，如果用Firefox的Downthemall来下载更是无语，下载一大半然后又自动重下。

于是我想着能不能先把迅雷离线服务器上的东西下载到vps上，然后在从vps下载到自己电脑上。试了下还是可以实现的，关键是要把浏览器的cookie导出来，然后wget或aria2使用这个cookie来连接服务器就可以登录了。

Firefox的cookie可以用Export Cookies导出（Chrome暂时没有找到什么方法导出cookie），然后将cookies.txt上传到vps; 迅雷离线服务器下载好了以后，选择资源复制下载链接; 然后`wget –load-cookies=cookiefile 'url' -o outputfilename` 就可以了。如果觉得wget不够快，可以换用aria2多线程下载，加上参数-s，`aria2c –load-cookies=cookiefile -s 5 'url' -o outputfilename`，就是将文件分成5份来下载。等到vps下载好了之后就可以用sftp，ftp，http等方法把文件下载到自己的电脑了。

[xunlei]: http://lixian.xunlei.com
