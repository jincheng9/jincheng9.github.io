---
layout: page
title: Step by Step
tagline: 
---
{% include JB/setup %}


## Technical Posts 


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


GitHub: [https://github.com/jincheng9](https://github.com/jincheng9) 

Email:[perfume0607@gmail.com](perfume0607@gmail.com)
