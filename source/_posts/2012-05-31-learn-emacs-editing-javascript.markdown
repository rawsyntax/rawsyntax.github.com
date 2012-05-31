---
layout: post
title: "Learn Emacs: Editing Javascript"
date: 2012-05-31 17:07
comments: true
categories: ["learn-emacs"]
---

One of my favorite things about emacs is its javascript modes.  While
there are a million options, I'm only going to talk about how I edit
javascript with emacs.

##  Which Mode do I Use?

I use [js2-mode](http://code.google.com/p/js2-mode/).  It provides
syntax highlighting and underlines errors as you type.  This mode
doesn't come with emacs, it was built by Steve Yegge.  However it is
installable through the ELPA.

One problem I found with this mode is that it has some weird ideas
about indentation.  I personally prefer the indentation from the
built-in `js-mode` in emacs.  After some googling I came across a
[blogpost](http://mihai.bazon.net/projects/editing-javascript-with-emacs-js2-mode)
on fixing indentation in `js2-mode`.  Starting with that I then made my
own modifications and have a `js2-mode` that works exactly the way I
want it (code below).

{% gist 2846385 %}

## Editing Javascript in HTML

In my experience I'm not always editing pure `.js` files.  Sometimes
I'm editing javascript inside a `.haml`, `.erb`, or `.html` file.  The
`haml-mode` I am using is supposed to have easy `js-mode` integration.
However I tried to integrate `js2-mode`, and it was not simple.
Furthermore, the built-in javascript highlighting seems to break on a
regular basis.  Troubleshooting that problem looked like it was going
to take more time than I had. Instead I wrote some elisp to allow me
to quickly create a javascript scratch buffer.

## Javascript Scratch Buffer

I use this to write javascript and copy / paste between buffers until
I'm happy with the code.  It's a very simple solution to the problem.
It creates a buffer named scratch-js with `js2-mode`.  It's not unlike
the elisp scratch buffer that comes up on emacs start up.  I don't
write javascript all the time, so this solution works pretty well for me.

{% gist 2846414 %}

This is admittedly a stopgap solution.  I would prefer to have
`js2-mode` integrated tightly with `haml-mode`.  If anyone else has
actually done this, I would love to see the code.
