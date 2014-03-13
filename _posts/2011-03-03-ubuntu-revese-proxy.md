---
layout: post
title:  "ubuntu ppa反向代理"
category: tech
tags: [linux, ubuntu, ppa, proxy]
---
用ubuntu的同学都知道ppa源的速度特别慢，于是刚在国外vps上建了反向代理，加速ppa的下载。

自己试了下速度很快，截图

![ubuntu]({{ site.img_url }}/ubuntu.png)

这是平均速度 

要使用的同学请修改/etc/hosts文件，添加:

{% highlight bash %}
2607:f878:3:2:0:300:2213:10 ppa.launchpad.net

2607:f878:3:2:0:300:2213:10 keyserver.ubuntu.com

2607:f878:3:2:0:300:2213:10 launchpad.net
{% endhighlight %}

暂时只有ipv6可以连接，希望大家能够反馈使用效果。 
