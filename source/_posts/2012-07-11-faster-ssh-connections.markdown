---
layout: post
title: "Faster SSH Connections"
date: 2012-07-11 12:34
comments: true
categories: ["tools"]
---

Certain servers I connect to on a regular basis are rather slow when
connecting.  Here are some `~/.ssh/config` options to speed up ssh connections.

I find this is useful for scripts that make multiple subsequent ssh
connections.  Capistrano comes to mind as well as a couple of scripts
I have that use scp.

{% gist 3091626 %}
