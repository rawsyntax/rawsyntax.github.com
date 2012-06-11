---
layout: post
title: "Troubleshooting your Emacs Config"
date: 2012-01-22 22:26
comments: true
categories: ["programming", "learn-emacs"]
---

Up to this point my [Learn Emacs](/blog/categories/learn-emacs)
series has been all about how to do cool stuff in emacs.  One of my
personal favorites is [align-regexp](/blog/learn-emacs-align-regexp/).
A while back that stopped working for me.  Now I get an error: `Wrong type
argument: markerp, 0`.  Emacs doesn't always do what I mean.

<!--more-->

### First Remove your Config

Whether you use a single `.emacs` file or a `~/.emacs.d/` directory
it is time to remove it.  Personally I keep `~/.emacs.d/` symlinked to
my [emacs.d github repo](https://github.com/rawsyntax/emacs.d) so it iss
quite easy to remove the symlink.  Alternatively you can start emacs
with the `--no-init-file` option, to skip loading your files. The
rationale for removing your config is simply that it reduces the
number of variables you are dealing with.  Is the problem with your
config or with emacs itself?

### Then Check your Emacs Version

After I removed my config and tried `M-x align-regexp` again, I got
the same error.  So its not my config.  If you find you have a problem
with a particular version of emacs `M-x emacs-version` will tell you
what version you have.  In my case it was

    GNU Emacs 24.0.92.1 (x86_64-apple-darwin, NS apple-appkit-1038.36) of 2011-12-02 on bob.porkrind.org

As I get my emacs builds from
[EmacsForMacOSX](http://emacsformacosx.com/) or `brew install` them
myself.  At this point I'm fairly certain I'm getting the error as a
result of running a nightly build.  A quick google leads me to
[bug#10249: 24.0.92](http://lists.gnu.org/archive/html/bug-gnu-emacs/2011-12/msg00266.html).
I installed a pretest version, and align-regexp works fine like it
used to..  I would prefer to be running the stable version, but I'm using
[emacs-starter-kit](https://github.com/technomancy/emacs-starter-kit)
for my config, which requires emacs 24.

### Version your Config

When functionality like this breaks it is really awesome to have an
emacs configuration that is under version control.  I can walk
backwards through any recent changes to find what is causing breakage.
So if your config isn't already versioned, version it right now.

PS: I'm interested to know any emacs topics you'd like to see a
blogpost on.  I haven't been hacking my emacs config much lately, so
I'm short on ideas for emacs posts.
