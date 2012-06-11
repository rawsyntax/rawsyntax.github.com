---
layout: post
title: Start Using html5
alias: [/post/4542811266/start-using-html5, /post/4542811266]
---

There's a lot of hype going on about html5 nowadays. If you're not
using html5 yet, the whole thing can be somewhat overwhelming. After
reading this blogpost you'll be ready to upgrade your current project
(or start a new one) using html5.

<!--more-->

## Understanding html5

I went to the [bocaruby](http://www.meetup.com/bocaruby/) ruby users group earlier this month. I had some understanding of what html5 is capable of, but Diego Scataglini's presentation [html5 a gentle introduction](http://diegoscataglini.com/2010/09/14/232/html-5-a-gentle-introduction/) definitely expanded my knowledge. I recommend it as a solid introduction to what is different about html5.

## Using html5

Often times after learning about a new technology a lot of programmers get stuck. This new functionality is great, but how I do I get started using it? It really helps to have something that gives you a little push.

[enter html5-boilerplate](http://html5boilerplate.com/)

Its a frontend template written in html5 with a lot of goodness baked in from the start. Between the css, html, various server configuration files, javascript libraries and profiling, its a huge collection of sane defaults for any web project.

Some of its many features

+ [Modernizr](http://www.modernizr.com/)
+ [html5 css reset](http://html5doctor.com/html-5-reset-stylesheet/)
+ cross-browser compatible
+ cdn hosted jquery with local fallback
+ javascript profiling I particularly like how it handles ie specific styles.

{% gist 595804 %}

You end up with a ie-version class applied to the html tag, which allows you to do ie targeted css all in the same file. For example:

{% gist 595820 %}

## Getting the code

You can get html5-boilerplate on the [official site](http://html5boilerplate.com) or [github](http://github.com/paulirish/html5-boilerplate)

[sporkd](http://github.com/sporkd) has created a compass plugin for html5-boilerplate [get the code here](http://github.com/sporkd/compass-html5-boilerplate)
