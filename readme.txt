1. _site目录下的所有文件都是根据root目录下的md文件或者html文件生成的

2. 决定网站要显示的page
在jincheng9.github.io这个目录下方的html文件名就是在首页会显示的page
html里的内容参考根目录下其它如archive.html怎么写的: 只需要复制以下内容即可

---
layout: page
title: About
header: About Myself
group: navigation
---
{% include JB/setup %}

添加标签页面： 比如我要放一个about标签在网站上，就先rake page name = "about.md"，在about.md
里用markdown语法写内容。写完之后，如果放到GitHub上，这事GitHub server会自动生成一个
about.html在_site目录下，about标签还不会显示在网站上，这个时候在repo根目录，新建一个
about.html，往里面拷贝上面的内容，再上传到GitHub，过一会，网站上就会显示About标签

删除标签页面：在根目录下删除对应的html文件即可

love.html在根目录下，但是没有显示在首页的标签页是因为love.html开头没有类似about.html开头的那些语句块。


3. page的内容
修改page对应的md文件或者根目录下的html文件

注意： 直接修改_site目录下文件无效，因为_site目录下文件都是根目录文件生成的。

a. 往根目录放的对应page的md文件，会生成_site目录下的html文件
b. 往根目录放的html文件，css文件夹和js文件夹， 会直接复制到_site目录下
c. _posts/目录下的post对应的md文件，会生成_site目录下post对应的index.html
d. 往根目录放一个about.html，网站对应的也会在首页增加about标签，不需要自己去修改_site目录下的html，修改也没用


4. GitHub现在不支持rouge，本地调试用rouge，上传到GitHub用pygments

5. 参考如下url来添加page和post
http://jekyllbootstrap.com/usage/jekyll-quick-start.html

6. 添加project page
   rake page name="project/project_name.md"
   然后往project_name.md里添加内容即可
   然后可以在jincheng9.github.io/project/project_name.html查看
   
7. 添加post
   rake post title="hello world", =左右不加空格
   会在_post/ 目录下生成一个hello-world.md，往这个文件添加内容即可
  
8. 添加image
   可以用markdown语法或者插入html代码
   <img src="img path" alt="img description" style="width:666px;">
   img path如果直接用/a表示从jincheng9.github.io这个目录开始下的子目录a
   img path如果直接用./a表示这个文件所在目录下的子目录a
   / 表示根目录  ./表示当前目录
9. 关闭右上角search功能
   其实右上角search功能一点用没有，不能进行搜索，可以在\_includes\themes\bootstrap-3\default.html里注释掉search
   