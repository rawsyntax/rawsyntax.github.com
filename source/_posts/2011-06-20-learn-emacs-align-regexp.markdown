---
layout: post
title: "Learn Emacs: align-regexp"
categories: [learn-emacs]
alias: [/post/6724439481/learn-emacs-align-regexp, /post/6724439481]
---

In this post I go over how to use emacs and align-regexp to clean up
your code and make it more readable.

<!--more-->

#### From the Emacs Manual:

align-regexp is an interactive autoloaded Lisp function in `align.el'.

It is bound to C-x .

(align-regexp BEG END REGEXP &optional GROUP SPACING REPEAT)

Align the current region using an ad-hoc rule read from the minibuffer. BEG and END mark the limits of the region. This function will prompt for the REGEXP to align with. If no prefix arg was specified, you only need to supply the characters to be lined up and any preceding whitespace is replaced. If a prefix arg was specified, the full regexp with parenthesized whitespace should be supplied; it will also prompt for which parenthesis GROUP within REGEXP to modify, the amount of SPACING to use, and whether or not to REPEAT the rule throughout the line. See `align-rules-list' for more information about these options.

For example, let's say you had a list of phone numbers, and wanted to align them so that the opening parentheses would line up:

    Fred (123) 456-7890
    
    Alice (123) 456-7890
    
    Mary-Anne (123) 456-7890
    
    Joe (123) 456-7890

There is no predefined rule to handle this, but you could easily do it using a
REGEXP like "(". All you would have to do is to mark the region, call `align-
regexp' and type in that regular expression.

## What I use align-regexp for

{% gist 1035839 %}
