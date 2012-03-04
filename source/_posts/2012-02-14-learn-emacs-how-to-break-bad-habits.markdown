---
layout: post
title: "Learn Emacs: How to Break Bad Habits"
date: 2012-02-14 10:10
comments: true
categories: ["learn-emacs"]
---

<img src="/images/arrow-keys.jpg" class ="center"/>

The best thing to do is never to form bad habits in the first place.
However if you didn't have any bad habits, you wouldn't be reading
this blog post.  Here's what has worked for me.

### Make a Note of It

One of my bad habits was using the arrow keys for navigation in emacs.
It's inefficient.  Emacs already has keybindings for next / previous
and back / forward -- and I don't have to pick up my hands for those.
The first thing I did was start keeping a short list of bad emacs
habits.

Don't think about fixing every bad habit immediately.  Just note them
and move on with real work.  These also don't have to be bad habits
per say.  They can be inefficiencies as well.  Is there a better way to
do that thing you do all the time, but you've been putting off putting
in the time to build it?

### Fix One Bad Habit

After years of using the arrow keys in emacs, I decided it was time
for that to stop.  Because my emacs config is versioned.  I can see
that I decided to stop on `Fri Sep 16 10:53:49 2011 -0400`.  Work on
fixing this one habit until its completely fixed.  My fix was pretty
simple.

{% gist 1794878 %}

Unbind the arrow keys and it becomes pretty tough to use them.  I
don't use the arrow keys any more.  Maybe your fix is more complicated.
Maybe it's writing an emacs macro for something you do frequently.

### Schedule Time for This

Its a bad idea to try to fix emacs problems while on a tight deadline
for a project.  However you will find yourself with a spare 30 minutes
or an hour here and there.  Make that your emacs improvement time.

Almost a year ago I found myself with an ever growing emacs problem.
My config files had grown out of control.  They were a huge mess and
impossible to manage.  Even though I was using version control my
config still had lots of local changes and files that weren't tracked
at all.  And my github repo was never up to date. I was in need of a
fresh emacs config.  I needed organization and simplicity.

When would I ever have time to rewrite my entire emacs config?

I started making time on `Tue Jun 21 18:18:41 2011 -0400` as I had read
about `emacs-starter-kit (v2)`.  Its basis was emacs-24 paired with
the marmalade-repo (for emacs-lisp packages).  I put in an n hour here
and there over the course of a few months.  In mid September it was good
enough to use as my full-time working config.
