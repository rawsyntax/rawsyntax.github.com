---
layout: post
title: "Learn Emacs: use defadvice to modify functions"
categories: [learn-emacs]
---

I use defadvice to change the behavior of zap-to-char. In it’s original form, zap-to-char deletes all characters up to and including the matching character. I prefer it to behave more like zap-up-to-but-not-including-char. It’s more intuitive to me.

{% gist 1038120 %}

More on defadvice [here](http://www.gnu.org/s/emacs/manual/html_node/elisp/Advising-Functions.html)
