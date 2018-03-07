---
title: Liquid Exception Exec format error
date: 2018-03-07 04:22:24 Z
categories:
- Openwrt
layout: post
---


if you receive an error like:

{% highlight ruby %}
Liquid Exception: Exec format error C:\....
{% endhighlight %}

You can try to change inside the file _config.yml the:

{% highlight ruby %}
highlighter: pygments
{% endhighlight %}

to

{% highlight ruby %}
highlighter: pygments.py
{% endhighlight %}


