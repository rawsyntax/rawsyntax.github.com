---
layout: post
title: "The Problem with &#xb5;-Frameworks"
date: 2011-11-27 11:34
comments: true
categories: ["rants"]
---

<img src="/images/simple-spaghetti.jpg" class ="center"/>

There are plenty of micro-frameworks out there for web development.
Some ruby based ones are Sinatra, Padrino, and Camping.  There's also
Flask and web.py for python.  These frameworks promise quick ramp up
time and simplicity.  They are small and do not provide much
functionality, which is sold as "not getting in your way".

<!--more-->

### Great! What's not to like?

In theory this sounds super, and if you have a project that has a very
limited scope it works very well.  I'm not going to talk much about
that case.  I find the more common case is that the project grows beyond its
original specification.  Then suddenly you may need some of those
features that were stripped out in order for the framework not to get
in your way.  You're left with two options: write the feature yourself
or find a plugin that implements it.

### Missing Features for Managing Complexity

It can be argued that software development is all about managing
complexity.  Often micro-frameworks strip out useful features in the name
of simplicity.  For example, Sinatra does not come with an acceptable
partials implementation.  Its implementation allows you to render
partials so long as there are no instance variables to be passed in.
It is only useful for static html partials.  This omission just makes
programming with sinatra harder.  Partial Rendering is a feature that helps reduce complexity.  It serves to break up large complex views into smaller manageable pieces and also DRY up the code.

### Fat App on a Thin Framework

<img src="/images/complex-spaghetti.jpg" class ="center"/>

Pretty soon you find yourself managing a project on a micro-framework
with 10 external plugins for the various functionality that was not
included out of the box.  So now you're using a micro-framework that
is no longer so simple.  Its intent to stay out of your way has
actually made things harder now since your upgrade path is more
complex.  When you upgrade the micro-framework how many of your
plugins will still work?  How does the complexity of a micro-framework
and 10 plugins compare to a regular framework (rails in the case of
sinatra)?  You also have to be sure that the combination of plugins
you are using do not conflict with eachother and cause unintended side-effects.

### Thin App on Fat Framework

For the project that grows beyond its initial scope, I prefer to start
with a thin application on top of a fat framework.  There's just less
for me to maintain and to test.  In the early days of the project its a really small app, and then when it grows larger it doesn't
start working against the framework.

### Micro-Frameworks are Only Good for Micro-Projects

This is not meant to disparage all the micro-frameworks out there.  I
believe they solve a specific problem.  I use micro-frameworks when
the project is a good fit for them.  However, knowing a
micro-framework really well is not a good excuse for not knowing a
more powerful framework.  Sometimes the more powerful framework is
what is needed.
