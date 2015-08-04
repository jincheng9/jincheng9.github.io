---
layout: post
title: "Git同时配置多个网站账号"
description: "Git同时配置多个网站账号, github, gitlab, ssh key"
category: [工具]
tags: [git]
---
{% include JB/setup %}
一. 前言
===
我们在工作的时候经常需要在一台电脑上将git与多个网站相关联，比如GitHub和GitLab，在这种情况下，
我们要为不同的网站配置不同的用户信息和ssh key。那怎么在一台电脑上为git配置多个网站的用户信息和ssh key呢？

二. 软件下载
===
测试环境Win7，用msysgit，软件链接：http://msysgit.github.io

三. 配置GitHub网站
===

我们先在计算机本地创建一个文件夹，假设叫github，我们将GitHub相关的工程都放在github文件夹，从git bash进入github文件夹，然后执行如下命令：
{% highlight sh %}
	git init
{% endhighlight %}
然后执行如下操作	

(1) 配置用户名和邮箱，邮箱是注册GitHub的邮箱
	{% highlight sh %}
git config user.name "jincheng9"
git config user.email "perfume0607@gmail.com"
	{% endhighlight %}
(2) 生成新的SSH Key，执行下面这条命令的时候可以输入文件名来保存私钥，假设为id_rsa_github
	{% highlight sh %}
    ssh-keygen -t rsa -C "perfume0607@gmail.com"
	{% endhighlight %}
(3) 确保ssh-agent已被启用
{% highlight sh %}
	eval $(ssh-agent -s)
{% endhighlight %}
(4) 添加SSH Key到SSH agent
{% highlight sh %}
	ssh-add id_rsa_github
{% endhighlight %}	
(5) 添加SSH Key到网站账号设置里
{% highlight sh %}
    clip < id_rsa_github.pub
{% endhighlight %}	
(6) 测试SSH连接
{% highlight sh %}
	ssh -T git@github.com
{% endhighlight %}	

四. 配置GitLab网站
===
我们先在计算机本地创建一个文件夹，假设叫gitlab，我们将GitLab相关的工程都放在gitlab文件夹，从git bash进入gitlab文件夹，然后执行如下命令：
{% highlight sh %}
	git init
{% endhighlight %}
然后执行如下操作	

(1) 配置新的网站的用户名和邮箱，邮箱是在GitLab上注册的邮箱
	{% highlight sh %}
git config user.name "zhangjincheng"
git config user.email "zhangjincheng@company.com"
	{% endhighlight %}
(2) 生成新的SSH Key，执行下面这条命令的时候可以输入文件名来保存私钥，假设为id_rsa_gitlab
	{% highlight sh %}
    ssh-keygen -t rsa -C "zhangjincheng@company.com"
	{% endhighlight %}
(3) 确保ssh-agent已被启用
{% highlight sh %}
	eval $(ssh-agent -s)
{% endhighlight %}
(4) 添加新的SSH Key到SSH agent
{% highlight sh %}
	ssh-add id_rsa_gitlab
{% endhighlight %}	
(5) 添加SSH Key到GitLab网站账号设置里
{% highlight sh %}
    clip < id_rsa_gitlab.pub
{% endhighlight %}	

(6) 创建config文件

进入Git Bash，在~目录，有一个.ssh文件夹，在这个文件夹里创建一个config文件
{% highlight sh %}
cd ~/.ssh
touch config
{% endhighlight %}	
config里要添加的内容如下：
{% highlight sh %}
# github
Host github.com
HostName github.com
PreferredAuthentications publickey
IdentityFile F:/github/id_rsa_github

# gitlab
Host gitlab.com
HostName 192.168.10.93
PreferredAuthentications publickey
IdentityFile F:/gitlab/id_rsa_gitlab
{% endhighlight %}	

(6) 测试SSH连接
{% highlight sh %}
	ssh -T git@gitlab.com
{% endhighlight %}	

五. 工作流程
===
(1) 对GitHub的repo就在github目录下操作，对GitLab的repot就在gitlab目录下操作

(2) 在comit的时候，如果提示：*** Please tell me who you are，就执行一条config语句：
{% highlight sh %}
	git config user.email "email of the corresponding website"
{% endhighlight %}	
或者在这个repo所在目录下的文件.git/config的最后，添加如下内容：
{% highlight sh %}
[user]
        email = perfume0607@gmail.com
{% endhighlight %}
		

