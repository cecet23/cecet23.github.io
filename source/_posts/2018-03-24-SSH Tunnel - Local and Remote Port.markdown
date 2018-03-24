---
title: SSH Tunnel - Local and Remote Port!
date: 2018-03-24 12:07:24 Z
categories:
- ssh
- local
- remote
layout: post
---

magine you’re on a private network which doesn’t allow connections to a specific server. Let’s say you’re at work and imgur.com is being blocked. To get around this we can create a tunnel through a server which isn’t on our network and remote server.
{% highlight shell_session %}
ssh user@remoteserver -L localport:locahost:remoteport
{% endhighlight %}

The key here is -L which says we’re doing local port forwarding. Then it says we’re forwarding our local port  to remoteport, which is the default port for HTTP. Now open your browser and go to http://localhost:localport.

