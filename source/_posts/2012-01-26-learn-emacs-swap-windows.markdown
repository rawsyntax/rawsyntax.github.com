---
layout: post
title: "Learn Emacs: Swap Windows"
date: 2012-01-26 10:33
comments: true
categories: ["learn-emacs"]
---

When I use Emacs in GUI mode, I set it up to have two 80 column
windows side by side.  It's extremely convention when you need to look
at one section of the code while writing another.  For instance, you
can have the spec file side by side with the code when doing TDD.
Sometimes I want to swap the windows.  This kind of functionality does
not come built in with emacs.  I found the `swap-windows` function
that I use in Steve Yegge's
[.emacs](https://sites.google.com/site/steveyegge2/my-dot-emacs-file)
file.

{% gist 1683375 %}


