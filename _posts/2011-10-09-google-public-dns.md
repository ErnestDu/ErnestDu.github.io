---
layout: post
title: "Google Public DNS IPv6 addresses"
description: ""
category: tech
tags: [dns, google, ipv6, network]
---
{% include JB/setup %}

也不知道什么时候有的，今天才发现。

[Google Public DNS IPv6 addresses:][google-dns]

{% highlight bash %}
2001:4860:4860::8888

2001:4860:4860::8844
{% endhighlight %}

这ip还算好记，不过暂时不会像ordns.he.net(2001:470:20::2)那样返回Google相关域名的ipv6地址。

另外今天才知道为什么在不同的地点ping 8.8.8.8, 2001:470:20::2或者2001:4860:4860::8888这些ip都很快的原因，因为它们使用了anycast任播技术，实际的服务器是分布在很多不同地理位置的，比如全球13个根域名服务器”a~m.root-servers.net”，其中部分并不只有单一个服务器，是以任播技术在全球多个地点设立镜像站。好嘛，我觉得需要去补计算机网络知识了。

[google-dns]: https://developers.google.com/speed/public-dns/docs/using
