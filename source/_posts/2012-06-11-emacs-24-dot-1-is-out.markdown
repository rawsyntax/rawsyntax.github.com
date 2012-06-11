---
layout: post
title: "Emacs 24.1 is Out"
date: 2012-06-11 16:55
comments: true
categories: ["learn-emacs"]
---

Emacs 24.1 was
[released](http://lists.gnu.org/archive/html/emacs-devel/2012-06/msg00164.html)
yesterday.

Being the first release version of Emacs 24, I'd suggest trying it
out.  I've been using Emacs 24 since the pretest version started
coming out, and even the recent pretests have been stable for me.

<!--more-->

## Some New Features

My favorite feature of Emacs 24 is the elisp package manager.  I find
its an extremely convenient way to manage the packages you want your
`~/.emacs.d` to utilize. It's available via `M-x list-packages`.  The
canonical package manager is known as the
[ELPA](http://tromey.com/elpa/), but there are other package
managers, such as [marmalade](http://marmalade-repo.org/) because the
ELPA doesn't include everything.

Getting the package manager setup is easy.  Here's the minimal code
needed:

{% gist 2912673 %}

Another new feature is the built-in color-theme facility.  Prior to
Emacs 24 color themes could be created through the
[color-theme](http://www.emacswiki.org/cgi-bin/wiki?ColorTheme)
package.  Instead you can now use `customize-create-theme` to create
color-themes.

<img src="/images/customize-create-theme.jpg" class ="center"/>

There's too much to cover in a blogpost, but here's the entire
[NEWS file](https://www.gnu.org/software/emacs/NEWS.24.1), which you
can also view inside emacs with  `M-x view-emacs-news`.
