---
layout: post
title: "Git同时配置多个网站账号"
description: "Git同时配置多个网站账号"
category: [工具]
tags: [git]
---
{% include JB/setup %}
1. 前言
===
我们在工作的时候经常需要在一台电脑上将git与多个网站相关联，比如GitHub和GitLab，在这种情况下，
我们要为不同的网站配置不同的ssh key。那怎么在一台电脑上为git配置多个ssh key呢？我们只需要在
.ssh目录下创建一个config文件配置各个网站的ssh key就可以了

2. 软件下载
===
测试环境Win7，用msysgit，软件链接：http://msysgit.github.io

3. 配置第一个网站
===
(1) 配置用户名 
	{% highlight sh %}
	git config --global user.name "YOUR NAME"
	{% endhighlight %}

(2) 配置邮箱
	{% highlight sh %}
	git config --global user.email "YOUR EMAIL ADDRESS SPECIFIED in YOUR WEBSITE"
	{% highlight sh %}

(3) 生成新的SSH Key
	{% highlight sh %}
    ssh-keygen -t rsa -C "YOUR EMAIL ADDRESS SPECIFIED in YOUR WEBSITE"
	{% highlight sh %}
(4) ensure ssh-agent is enabled

	eval $(ssh-agent -s)
	
(5) add your ssh key to the ssh agent

	ssh-add ~/.ssh/id_rsa
	
(6) add your ssh key to your account

    clip < ~/.ssh/id_rsa.pub，然后将key粘贴到网站的ssh keys设置下
	
(7) test the connection

	ssh -T git@website.com
	
4. 配置第二个网站
===




