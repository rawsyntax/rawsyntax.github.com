---
layout: post
title: Puncher the simple file watcher for OS X
categories: ["ruby","code"]
alias: [/post/4543965752/puncher-the-simple-file-watcher-for-os-x, /post/4543965752]
---

Why another file watcher for OS X?

There's already [kicker](http://github.com/alloy/kicker), and many ruby programs that need file watching, already have solutions built in. For example [ZenTest](http://github.com/seattlerb/zentest), [compass](http://compass-style.org) etc..

The problem with file watchers on OS X is that they depend on [rubycocoa](http://rubycocoa.sourceforge.net/HomePage). If [rubycocoa](http://rubycocoa.sourceforge.net/HomePage) isn't available most of them fallback to [file-system polling](http://bit.ly/dDnkCu), which kills my cpu. If you're using the system ruby that comes with OS X, you're fine because [rubycocoa](http://rubycocoa.sourceforge.net/HomePage) is already built in.

I use [rvm](http://rvm.beginrescueend.com/), which makes it super easy for me to install multiple separate and self-contained versions of ruby. I could for instance, maintain an old project that was written against ruby-1.8.6 while on the same machine starting a new project using ruby-1.9.2.

You'll only run into [rubycocoa](http://rubycocoa.sourceforge.net/HomePage) problems if you use [rvm](http://rvm.beginrescueend.com/). Have a quick [google for rvm and rubycocoa](http://www.google.com/search?&q=rubycocoa+rvm), and you'll see a huge list of people having issues installing rubycocoa with rvm.

Typically the code to fix this problem goes something like this

{% gist 289868 %}

Eventually, I got tired of having to install rubycocoa just to use osx's fsevents. I discovered [ruby-fsevent](http://github.com/sandro/ruby-fsevent) when I went looking for solutions to this problem. It's a file watcher gem with a C extension that uses fsevents. For me this means I don't have to fuss with recompiling my ruby version and and making rvm and rubycocoa happy to get fsevents.

However, there still was a problem. [Compass](http://compass-style.org) doesn't use ruby-fsevent. I needed a file watcher that uses ruby-fsevent and does not depend on rubycocoa, and can execute arbitrary commands. I wanted a tool that I could use like below.

`puncher 'command' files_in_dir/*`

And that's what I built. It's incredibly simple. The code is only 29 lines.

{% gist 603206 %}

Today I mostly use it like below

`screen -S compass_punch puncher 'bundle exec compass -c config/compass.rb' app/sass/*`

This creates a screen, which runs a puncher instance, that runs a compass command to compile all my sass code, whenever a sass file is modified. Even though compass requires rubycocoa for using fsevents, I can wrap it with my puncher gem and use fsevents without rubycocoa.

I wrap it in a screen so I can check on the output occasionally. My next enhancement is to add growl notifications to puncher, then I can simply background the process, instead of spawning a screen for it. Problem solved.

PS if you have any interest in seeing a version of puncher that works on linux or windows, send me a message, comment, or create an issue on the github issue tracker.

UPDATE: I heartily recommend [guard](https://github.com/guard) for general purpose file watching
