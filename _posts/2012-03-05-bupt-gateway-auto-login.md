---
layout: post
title: "北邮校园网登录脚本（Shell & Greasemonkey）"
description: ""
category: tech
tags: [shell, javascript, bupt, firefox, chrome, userscript, network]
---
{% include JB/setup %}

学校的网络自从启用登录验证后总有些不方便，虽然有客户端，但是我一直对这类软件比较讨厌。

不过还是有办法的，查看登录页面的源代码，发现登录的时候把密码是md5加密后和用户名以及其他信息POST到服务器；注销密码没有加密。

[Shell脚本][github]（点击下载）

可以方便只用命令行的同学。功能只有登录和注销，-i 登录，-o 注销。使用前请先将yourname和yourpassword改为自己的用户名和密码。

[Greasemonkey脚本][userscript]（在Userscript的页面请另存为，不要直接安装）

这个写完结果发现很早之前有人写了 [http://bbs.byr.cn/#!article/NetResources/81527][byr] ，估计是学十的学长，但是认证网页改版后好像不能用了。 相比之下我这个更简陋，没办法，不会js，基本就是把登录页面的代码乱改了一下。。。

Firefox需要安装greasemonkey，Chrome直接就可以用，你们都懂的。

同样自己手动修改yourname和yourpassword为自己的用户名和密码，然后拖到浏览器里安装。 安装好以后未登录情况下打开浏览器会跳转到校园网网关登录页面，然后自动登录，半秒后跳转到你要访问的网页。

关于安全问题，用户名密码是本地明文保存的，登录时密码md5加密后截取了一部分POST到服务器，如果要觉得不要安全请慎用。

话说自从开始认证以后获取的ip都是10开头的了，以前的ip全都没有用了。

[byr]: http://bbs.byr.cn/#!article/NetResources/81527
[userscript]: http://userscripts.org/scripts/show/127461
[github]: https://github.com/ErnestDu/BUPTNet/raw/master/buptgw
