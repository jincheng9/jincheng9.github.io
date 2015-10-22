---
layout: post
title: "进程名和端口号互相查找"
description: "通过进程名查找端口号，通过端口号查找进程名"
category: 
tags: [tips]
---
{% include JB/setup %}

1 通过进程名查找端口号
===
* 先找到进程名对应的process id
  {%hightlight bat%}
  tasklist | findstr process_name
  {%endhighlight%}

* 通过process id找到该进程使用的端口号
  {%hightlight bat%}
  netstat -ano | findstr process_id
  {%endhighlight%}
  
2 通过端口号查找进程名
===
* 先找到端口号对应的process id
  {%hightlight bat%}
  netstat -ano | findstr port
  {%endhighlight%}

* 通过process id找到使用该端口的进程
  {%hightlight bat%}
  tasklist | findstr process_id
  {%endhighlight%}
  
  
