---
layout: post
title: "Reload your app with Guard and Pow"
date: 2012-02-22 15:06
comments: true
categories: ["programming", "ruby"]
---

About 6 months ago I started using [Pow](http://pow.cx/) for serving
my apps in development mode.  It loads any RACK compatible app, and
allows you to access your projects via the `.dev` and named symlinks
stored in `~/.pow` (for example `http://my_project.dev`).  No need to
specify a port either!

Very shortly afterwards I ran into a problem.  When I'm working on a
Sinatra app, normally I use the
[shotgun](https://github.com/rtomayko/shotgun) gem for automatic
reloading. I can't do that when I'm running Pow.  So I dug into Pow's
documentation.

Pow supports passenger-style reloads via these commands:

    touch tmp/restart.txt
    touch tmp/always_restart.txt

That's somewhat helpful.  However, remembering to run `touch tmp/restart.txt` every time I make a change is a pain.  Creating `tmp/always_restart.txt` reloads every time, but makes the app painfully slow.  I don't need a reload for every css / image / js asset that is fetched.

[Guard](https://github.com/guard/guard) to the rescue!  Guard is a
simple tool.  Watch files; run commands on change.  There is already a
[guard-pow](https://github.com/guard/guard-pow) gem.  Which touches
`tmp/restart.txt` on file change.

To use it, add `guard-pow` to your Gemfile.  Then define a Guardfile
telling it which files to watch.  Your specific files may differ, but
this works for my needs.

{% gist 1886987 %}

Finally, run `bundle exec guard`.  It will print when it restarts pow.
I like this approach because it can be adapted to any RACK compatible
app by changing which files get watched.  Also, it doesn't require you
to change any application specific code; It's only necessary to add
guard to the Gemfile.
