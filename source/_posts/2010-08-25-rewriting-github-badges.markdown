---
layout: post
title: Rewriting github-badges
categories: ["code", "javascript"]
alias: [/post/4542511982/rewriting-github-badges, /post/4542511982]
---

In building [rawsyntax](http://rawsyntax.com) I wanted to be able to
link to my [github profile](http://github.com/rawsyntax).

After a little searching I found
[drnic's github-badges](http://drnicjavascript.rubyforge.org/github_badge/).
It looked great, and I put it on the sidebar of my site. However, when
I went to do crossbrowser testing (I develop in firefox, and
crossbrowser test before deploying to production) I found that it
caused IE[6,7,8] to crash.

<!--more-->

This is a big problem. I believe strongly in
[graceful degradation / progressive enhancement](http://en.wikipedia.org/wiki/Progressive_enhancement). It's one thing if IE isn't getting the full experience, but crashing the browser is unacceptable.

At this point, I had to have github-badges on my site. It's simply too cool to
do without. Looking at the [github-badges project site](http://drnicjavascript.rubyforge.org/github_badge/) and the source code. I figured it'd be easier to re-implement than to debug the current code (mostly because I'd rather not debug on IE[6,7,8]).

In searching around for other github-badges alternatives, I didn't anything that looked good and actually worked in all browsers. I did happen upon [darkhax's make-your-own-badge-with-jquery-and-jaml](http://blog.darkhax.com/2010/03/04/make-your-own-badge-with-jquery-and-jaml) post. Between this and [drnic's github-badges](http://github.com/drnic/github-badges) I cobbled together a solution that works in all browsers, and has the same features as drnic's github-badges. It also has user configurable parameters. Check out the code on [github](http://github.com/rawsyntax/github-badge).

UPDATE: I've since removed the github-badges, and added a link to my profile instead

