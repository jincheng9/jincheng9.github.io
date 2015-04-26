1. _site目录下的所有文件都是根据root目录下的md文件或者html文件生成的

2. 决定网站要显示的page
在jincheng9.github.io这个目录下方的html文件名就是在首页会显示的page
html里的内容参考根目录下其它如archive.html怎么写的:

---
layout: page
title: About
header: About Myself
group: navigation
---
{% include JB/setup %}



3. page的内容
修改page对应的md文件或者根目录下的html文件

注意： 直接修改_site目录下文件无效，因为_site目录下文件都是根目录文件生成的。

a. 往根目录放的对应page的md文件，会生成_site目录下的html文件
b. 往根目录放的html文件，css文件夹和js文件夹， 会直接复制到_site目录下
c. _posts/目录下的post对应的md文件，会生成_site目录下post对应的index.html
d. 往根目录放一个about.html，网站对应的也会在首页增加about标签，不需要自己求修改_site目录下的html，修改也没用


4. GitHub现在不支持rouge，本地调试用rouge，上传到GitHub用pygments


