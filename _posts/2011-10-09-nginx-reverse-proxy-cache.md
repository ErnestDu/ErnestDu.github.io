---
layout: post
title: "让nginx反向代理使用缓存"
description: ""
category: tech
tags: [nginx, ipv6, network]
---
{% include JB/setup %}

为了不让每次通过ipv6访问blog时都要vps从虚拟主机那边读取数据浪费时间，可以在vps上建立缓存，加快速度。

直接贴在网上找的代码：

{% highlight bash %}
proxy_temp_path /home/cache/duxin/proxy_temp_dir 1 2;
proxy_cache_path /home/cache/duxin/proxy_cache_dir levels=1:2 keys_zone=duxin:50m inactive=1d max_size=1g;
server
{
	listen [::]:80;
	server_name blog.duxin.info;
	location / {
		proxy_pass http://blog.duxin.info;
		proxy_redirect  off;
		proxy_set_header        X-Real-IP $remote_addr;
		proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
		proxy_set_header        Host    $host;
		proxy_cache duxin;
		proxy_cache_valid 200 302 12h;
		proxy_cache_valid 301 1d;
		proxy_cache_valid any 1h;
		proxy_buffer_size 4k;
		proxy_buffers 4 32k;
		proxy_busy_buffers_size 64k;
		proxy_temp_file_write_size 64k;
	}
}

{% endhighlight %}
在chrome里面使用Page load time这个插件可以查看页面载入时间。nginx开启缓存前后页面载入速度对比：未开启 First response 716ms, Response end 402ms，开启后 First response 204ms，Response end 401ms，嗯，加速还是比较明显的。
