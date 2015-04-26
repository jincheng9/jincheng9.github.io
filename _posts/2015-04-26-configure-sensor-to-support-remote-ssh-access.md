---
layout: post
title: "configure sensor to support remote ssh access"
description: ""
category: [ssh]
tags: [ubuntu]
---
{% include JB/setup %}

## How to configure ubuntu to remote ssh access it?

{% highlight sh linenos %}
	sudo apt-get install openssh-serve
	sudo ufw allow 22
{% endhighlight %}

## Find specific processes running on ubuntu
1. Example: find processes suffixed with .py
{% highlight sh linenos %}
	ps -ef | grep .py
{% endhighlight %}

2. kill process with pid 7000
{% highlight sh linenos %}
	kill -9 7000
{% endhighlight %}

## upload file to ubuntu

use putty psftp, then unzip and install

## list file based on modified date
1. lastest file is at the bottom
{% highlight sh linenos %}
	ls -tr
{% endhighlight %}

2. oldest file is at the bottom
{% highlight sh linenos %}
	ls -t
{% endhighlight %}





