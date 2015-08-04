---
layout: post
title: "Git同时配置多个网站账号"
description: "Git同时配置多个网站账号"
category: [工具]
tags: [git]
---
{% include JB/setup %}
一. 前言
===
我们在工作的时候经常需要在一台电脑上将git与多个网站相关联，比如GitHub和GitLab，在这种情况下，
我们要为不同的网站配置不同的ssh key。那怎么在一台电脑上为git配置多个ssh key呢？我们只需要在
.ssh目录下创建一个config文件配置各个网站的ssh key就可以了

二. 软件下载
===
测试环境Win7，用msysgit，软件链接：http://msysgit.github.io

三. 配置第一个网站
===
(1) 配置用户名和邮箱
	{% highlight sh %}
	git config user.name "YOUR NAME"
	git config user.email "YOUR EMAIL ADDRESS SPECIFIED in YOUR WEBSITE"
	{% endhighlight %}
(2) 生成新的SSH Key
	{% highlight sh %}
    ssh-keygen -t rsa -C "YOUR EMAIL ADDRESS SPECIFIED in YOUR WEBSITE"
	{% endhighlight %}
(3) 确保ssh-agent已被启用
{% highlight sh %}
	eval $(ssh-agent -s)
{% endhighlight %}
(4) 添加SSH Key到SSH agent
{% highlight sh %}
	ssh-add ~/.ssh/id_rsa
{% endhighlight %}	
(5) 添加SSH Key到网站账号设置里
{% highlight sh %}
    clip < ~/.ssh/id_rsa.pub
{% endhighlight %}	
(6) 测试SSH连接
{% highlight sh %}
	ssh -T git@website.com
{% endhighlight %}	

四. 配置第二个网站
===
(1) 配置新的网站的用户名和邮箱
	{% highlight sh %}
	git config user.name "YOUR NAME"
	git config user.email "YOUR EMAIL ADDRESS SPECIFIED in YOUR WEBSITE"
	{% endhighlight %}
(2) 生成新的SSH Key，输入下面的命令的时候，会提示输入文件名来保存key，这个时候输入一个和第一个网站不同的文件名来保存新的key
	{% highlight sh %}
    ssh-keygen -t rsa -C "YOUR EMAIL ADDRESS SPECIFIED in YOUR WEBSITE"
	{% endhighlight %}
(3) 确保ssh-agent已被启用
{% highlight sh %}
	eval $(ssh-agent -s)
{% endhighlight %}
(4) 添加新的SSH Key到SSH agent
{% highlight sh %}
	ssh-add ~/.ssh/id_rsa_new
{% endhighlight %}	
(5) 添加SSH Key到网站账号设置里
{% highlight sh %}
    clip < ~/.ssh/id_rsa.pub
{% endhighlight %}	
(6) 测试SSH连接
{% highlight sh %}
	ssh -T git@website.com
{% endhighlight %}	



