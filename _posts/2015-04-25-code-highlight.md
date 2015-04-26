---
layout: post
title: "code highlight"
description: ""
category: 
tags: [python]
---
{% include JB/setup %}

## Python code

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