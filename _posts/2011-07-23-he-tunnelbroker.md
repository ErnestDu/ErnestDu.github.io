---
layout: post
title: "HE Tunnelbroker Server的选择"
description: ""
category: tech
tags: [ipv6, network, tunnelbroker]
---
{% include JB/setup %}
在家上网搜索Google总是被重置，还是学校的ipv6好。不过公网要用只能用隧道了，我选了he.net提供的tunnelbroker。

HE的服务器很多，ping了一下亚洲和北美的，然后比较之下选择了Seattle的服务器。现在下载byrbt基本能满速,youtube 720p也不卡。

{% highlight bash %}
Asia
Hong Kong, HK
--- 216.218.221.6 ping statistics ---
20 packets transmitted, 12 received, 40% packet loss, time 19009ms
rtt min/avg/max/mdev = 499.782/518.584/532.227/10.201 ms

Singapore, SG
--- 216.218.221.42 ping statistics ---
20 packets transmitted, 13 received, 35% packet loss, time 19008ms
rtt min/avg/max/mdev = 513.401/539.674/551.599/10.168 ms

Tokyo, JP
--- 74.82.46.6 ping statistics ---
20 packets transmitted, 12 received, 40% packet loss, time 19007ms
rtt min/avg/max/mdev = 355.273/367.665/379.252/7.338 ms

North America
Ashburn, VA, US
--- 216.66.22.2 ping statistics ---
20 packets transmitted, 11 received, 45% packet loss, time 19007ms
rtt min/avg/max/mdev = 429.345/443.857/455.826/8.973 ms

Chicago, IL, US
--- 209.51.181.2 ping statistics ---
20 packets transmitted, 9 received, 55% packet loss, time 19030ms
rtt min/avg/max/mdev = 261.513/282.285/302.296/12.008 ms

Dallas, TX, US
--- 216.218.224.42 ping statistics ---
20 packets transmitted, 14 received, 30% packet loss, time 19041ms
rtt min/avg/max/mdev = 268.863/285.936/300.166/10.401 ms

Fremont, CA, US
--- 72.52.104.74 ping statistics ---
20 packets transmitted, 16 received, 20% packet loss, time 19009ms
rtt min/avg/max/mdev = 333.407/355.904/366.239/9.376 ms

Los Angeles, CA, US
--- 66.220.18.42 ping statistics ---
20 packets transmitted, 12 received, 40% packet loss, time 19053ms
rtt min/avg/max/mdev = 339.233/352.516/365.890/8.120 ms

Miami, FL, US
--- 209.51.161.58 ping statistics ---
20 packets transmitted, 10 received, 50% packet loss, time 19037ms
rtt min/avg/max/mdev = 345.260/360.491/375.250/9.561 ms

New York, NY, US
--- 209.51.161.14 ping statistics ---
20 packets transmitted, 11 received, 45% packet loss, time 19051ms
rtt min/avg/max/mdev = 416.298/434.382/445.309/9.733 ms

Seattle, WA, US
--- 216.218.226.238 ping statistics ---
20 packets transmitted, 20 received, 0% packet loss, time 19019ms
rtt min/avg/max/mdev = 250.134/256.250/265.158/3.551 ms

Toronto, ON, CA
--- 216.66.38.58 ping statistics ---
20 packets transmitted, 14 received, 30% packet loss, time 18999ms
rtt min/avg/max/mdev = 525.444/542.232/559.514/11.509 ms
{% endhighlight %}

这里还找到个台湾的tunnelbroker列表

[http://tech.littlecho.tw/entry/IPv6-Tunnel-Brokers-in-Taiwan-and-IPv6-connectivity-test][link]
 
有空再测试一下速度。 

[link]: http://tech.littlecho.tw/entry/IPv6-Tunnel-Brokers-in-Taiwan-and-IPv6-connectivity-test
