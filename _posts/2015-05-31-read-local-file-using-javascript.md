---
layout: post
title: "read local file using javascript"
description: "read local files in javascript 用Javascript读取读取本地文件"
category: [javascript]
tags: []
---
{% include JB/setup %}

## Background
I was involved in a Hong Kong ITF project and the objective is to identify the [indoor white spaces](http://jincheng9.github.io/project/sensor_network.html) inside a building. To visualize the results, I need to build a web application. The requirements of this web application are mainly the following two aspects:

* read the real-time result stored in the computer
* show the results in a dynamic chart, with x-axis being the time

I searched on how to draw dynamic charts and found there are some good javascript libraries that can help me. So I decided to use
html+js to build this web application.


## Implementation

* How to read the local real-time result

The real-time result is stored in a file "data.txt". So I need to use javascript to read the data in "data.txt". But when I searched on how to use javascript to read data from file, I was a little surprised. Because javascript does not have file reading methods like C++, Python, PHP. The reason is that javascript does not have access to the user's file system due to security reasons. And the javascript method FileReader is only for files manually selected by the user. However, I want to use javascript to automatically read "data.txt" every 20 minutes without manually selection. 

After doing some search, I found my requirement can be done using javascript XMLHttpRequest() class. The idea is as follows:
although we cannot read local data, we can read data from webserver. So we can set up a local webserver, and then read data via
this local webserver using XMLHttpRequest(). The implementation steps are as follows:

1 install webserver on the computer (xampp is a good choice) and launch the webserver

2 write js code to read local data using XMLHttpRequest(). Below is the code (inside a html file, say wiser_sync.html)
	{% highlight javascript linoes%}

	var txtFile = new XMLHttpRequest();
	txtFile.open("GET", "data.txt", false); // "data.txt" can also be "http://127.0.0.1/data.txt"
	txtFile.onreadystatechange = function() {
		if(txtFile.readyState === 4) {
			var allText = txtFile.responseText;
			var data = allText.split(' '); // separate the data with space
			var ch1 = data[0];
			var ch2 = data[1];
			var ch3 = data[2];
		}
	}
	txtFile.send();

	{% endhighlight %}
	
3 Lanuch the html from chrome browser with the following url (Firefox seems does not work)

   http://127.0.0.1/wiser_sync.html
   

   
  


