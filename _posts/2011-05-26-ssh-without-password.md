---
layout: post
title:  "不输入密码登录ssh"
category: Linux
tags: [ssh, linux, putty, password]
---

使用ssh每次都要输入登录密码，感觉太麻烦，还是有办法不输入密码的。有两个办法，一种ssh是可以使用 authentication key登录的，另一种就是用expect自动输入密码。

##1. 用ssh密钥的办法：

###a. 本地生成密钥

ssh-keygen -t rsa

这会在~/.ssh/ 目录下生成id_rsa和id_rsa.pub两个文件，除了rsa以外还可以选择dsa，ecdsa这样的密钥，不过我没有试过了。

###b. 将生成的id_rsa.pub传到sshhost上面

`ssh-copy-id -i username@sshhost`

会提示输入密码，然后就会在sshhost的~/.ssh/目录下面生成authorized_keys这个文件，一切就ok了，以后登录就不用输入密码了。

##2. 用expect自动输入密码

如果没有权限使用ssh密钥的话可以用expect来自动输入密码，expect是Unix下面一个强大的进行自动化控制和测试的工具，@auxoro同学提供了个简单的脚本:

{% highlight bash %}
#!/usr/bin/expect

spawn ssh username@hostname

expect "password"

send "yourpassword\r";

expect eof

exit
{% endhighlight %}
其中username, hostname, yourpassword改成对应的用户名、主机名和密码，执行这个脚本就可以登录了，比较适合用ssh代理的情况。

以上两种方法相对于自己手动输入密码还是有点不安全的，第一种要是有人能够使用你的电脑就可以登录你的远程主机，第二种方法更是直接可以在脚本里面看到你的password了，所以要安全的话就还是不要怕麻烦再输入一遍密码好了。
