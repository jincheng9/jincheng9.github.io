---
layout: post
title: "code highlight"
description: ""
category: [blog]
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
1. Use the default highligher "pygments" in file _config.yml 

   GitHub does not support Rouge since August 1, 2014
   
2. Download a syntax highlighting css file (say syntax.css)

   You can borrow the file from this url: https://github.com/mojombo/tpw/blob/master/css/syntax.css
   
3. Add syntax.css to the directory: \assets\themes\bootstrap-3\bootstrap\css 

   Or other directories, make sure to refer syntax.css in step 4 correctly
  
4. include the css file to _includes\themes\bootstrap-3\default.html

   Refer to the way of including "bootstrap.min.css" 
   
## Setup Jekyll-Boostrap on GitHub

1. Create a Repo called jincheng9.github.io on GitHub

2. Push the contents of Jekyll-Boostrap to the Repo jincheng9.github.io

3. Modify the contents of index page

	Modify the index.md in the root directory
	
4. the files in root directory generate the files in _site directory

## How to add love.html to the website

Just add love.html, css folder and js folder to the root directory of jincheng9.github.io

Then the love.html, css folder and js folder will be automatically added to _site directory

Then you can vist love.html via: http://jincheng9.github.io/love.html

## References: 

Setup Jekyll-Boostrap: http://jekyllbootstrap.com/usage/jekyll-quick-start.html

Code Highlighting: 

1. http://jekyllrb.com/docs/templates/#code-snippet-highlighting

2. https://truongtx.me/2012/12/28/jekyll-bootstrap-syntax-highlighting/

   
