---
layout: post
title: "code highlight"
description: ""
category: 
tags: [python]
---
{% include JB/setup %}

## Python code highlighting example

{% highlight python linenos%}
import math

math.log10(100)

a = 10
if a>8:
	print("a<8")
	
def add(a, b):
	return a+b

def testCodeHighLight():
	print "good"
{% endhighlight %}

## How to Enable Code Highlighting in Jekyll-Boostrap
1. Use the default highligher pygments in file _config.yml 
   GitHub does not support Rouge since August 1, 2014.
   
2. Download a syntax highlighting css file (say syntax.css)
   You can borrow the file from this url: https://github.com/mojombo/tpw/blob/master/css/syntax.css
   
3. Add syntax.css to the directory: \assets\themes\bootstrap-3\bootstrap\css
  
4. include the css file to _includes\themes\bootstrap-3\default.html
   add this line: <link href="{{ ASSET_PATH }}/bootstrap/css/syntax.css" rel="stylesheet">

   
