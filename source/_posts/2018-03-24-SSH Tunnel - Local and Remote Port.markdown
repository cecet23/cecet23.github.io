---
title: SSH Tunnel - Local and Remote Port!
date: 2018-03-24 12:07:24 Z
categories:
- ssh
- local
- remote
layout: post
---

Imagine you’re on a private network or the remote network  doesn’t allow connections on a specific server on a specific port. To get around this we can create a tunnel from local connection to remote  server which isn’t on our network.
{% highlight shell_session %}
ssh user@remoteserver -L localport:locahost:remoteport
{% endhighlight %}

The key here is -L which says we’re doing local port forwarding. Then it says we’re forwarding our local port  to remoteport. Now open your browser and go to http://localhost:localport.

