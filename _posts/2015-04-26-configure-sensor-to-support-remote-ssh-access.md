---
layout: post
title: "configure sensor to accept remote ssh access"
description: "configure ubuntu to accept remote ssh access"
category: [ssh]
tags: [ubuntu]
---
{% include JB/setup %}

## How to configure ubuntu to accept remote ssh access?

{% highlight sh linenos %}
sudo apt-get install openssh-server
sudo ufw allow 22
{% endhighlight %}

## Find specific processes running on ubuntu
1 Example: find processes suffixed with .py
{% highlight sh %}
	ps -ef | grep .py
{% endhighlight %}

2 kill process with pid 7000
{% highlight sh %}
	kill -9 7000
{% endhighlight %}

## upload file to ubuntu

use putty psftp, then unzip and install

## list file based on modified date
1 lastest file is at the bottom
{% highlight sh %}
	ls -tr
{% endhighlight %}

2 oldest file is at the bottom
{% highlight sh %}
	ls -t
{% endhighlight %}

3 list the files that human can understand
{% highlight sh %}
	ls -lh
{% endhighlight %}

## Remotely run scripts without killing the process when exiting the ssh access
{% highlight sh %}
	nohup python master.py &
{% endhighlight %}





