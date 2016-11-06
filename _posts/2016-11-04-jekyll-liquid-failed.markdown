---
layout: post
title:  "jekyll-liquid-failed"
date:   2016-11-04
categories: ubuntu jekyll
---
今天心血来草想写个博客的时候突然发现前不久用github+jekyll搭建的博客炸了
打开index.html页面显示是这样的
{% raw %}
--- 　　layout: default 　　title: myBlog 　　--- 　　
{{ page.title }}

　　
new article

　　
　　　　{% for post in site.posts %} 　　　　　　
{{ post.date | date_to_string }} {{ post.title }}
　　　　{% endfor %} 　
{% endraw %}
然后一晚上就在各种谷歌，查看各种解决方案还是一个都没用
最后快放弃的时候突然发现我的index.html里的YAML头信息是这样写的
{% highlight ruby %}
    ---
    layout: post
    title:  "my first blog"
    date:   2016-11-04
    categories: jekyll
    ---
{% endhighlight %}
本着不浪费的原则我把他缩进缩回去了也就是这样
{% highlight ruby %}
---
layout: post
title:  "my first blog"
date:   2016-11-04
categories: jekyll
---
{% endhighlight %}
然后刷新一下了index.html页面的时候发现页面变成了这样
<img src="/image/Screenshot1.png" alt="Screenshot1"/>
好了。。。竟然好了我×××
冷静下来总结一下原因可能是我用atom打开index.html页面的时候它自己给我加上了空格
或者我自己不知道什么时候加上去的=!=
