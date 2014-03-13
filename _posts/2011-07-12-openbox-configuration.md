---
layout: post
title:  "Openbox配置记录"
category: tech
tags: [linux, openbox, software]
---

Gnome 3从发布以来用了好久，感觉不错，不过现在想换个口味了。但是KDE总感觉慢，而且感觉不怎么好看（我可能审美有问题），大家推荐的Awesome不是很习惯，于是就选了Openbox，搞了一个晚上，记录一下有些配置：

1.安装Openbox很简单

`pacman -S openbox`

2.另外还要安装个panel，我选了pypanel，还要obconf和obmenu设置工具：

`pacman -S pypanel obconf obmenu`

obconf可以设置主题，我就用clearlooks了，这个才是经典。

obmenu可以图像化地设置Openbox的菜单，不用自己编辑menu.xml文件了。

3.不知道为什么用了SLiM以后输入法fcitx就不能在gtk程序下调出了，把export那些环境变量改到autostart.sh里面也一样，于是还是用startx启动X。Fcitx输入法和pypanel都添加到autostart.sh里面，启动Openbox后就可以启动这些程序。

4.pypanel中文乱码，修改~/.pypanelrc 的字体设置就可以了，我用的是wenquanyi micro hei-8。

5.启动器安装了个kupfer，nautilus用thunar替换掉，gnome-terminal用xfce4-terminal替换掉，其他还有些程序慢慢再来。

6.纠结了很久的USB自动挂载：

首先添加用户到storage组`sudo pacman -a ernest storage`

然后添加hal到启动的daemon里面，在/etc/rc.conf里面

修改~/.xinitrc为`exec ck-launch-session openbox-session`

在thunar的preference里面enable volume management，把mount removable drives when hot-plugged勾上。

之前在Gnome 3下面设置的快捷键还能用，所以配置简单多了。以前也用过Openbox，设置壁纸要装feh，这次也不用，都是Gnome 3的设置，就不管了。大概就这些了。
