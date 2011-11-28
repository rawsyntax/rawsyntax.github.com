---
layout: post
title: "Solving the General Case"
date: 2011-11-28 16:05
comments: true
categories: ["programming"]
---

<a href="http://xkcd.com/974">
<img src="/images/the_general_problem.png" class ="center"/>
</a>

This XKCD comic struck a chord with me.  I feel that it presents a
false dichotomy.  Either miss deadlines to design it right or go wild
west cowboy coding and meet deadlines.  I think there's a middle ground between
those options.  Design it correctly, but deliver less functionality,
and add the rest of the functionality at a later date.  While that's a
simple solution, this comic touches on other related issues.

### Analysis Paralysis

<img src="/images/analysis-paralysis.jpg" class ="center"/>

This affliction is pretty common largely as a result of all the
choices we have nowadays when designing software.  Which language?
Which Framework? How about a
[Micro-Framework](/blog/the-problem-with-micro-frameworks/)?  Which
[Text Editor](/blog/categories/learn-emacs/)?  Nevermind questions
about how to actually solve the problem at hand.  If a simple flexible
design is not readily coming to mind, I find it helpful to write some
code that implements the very basics of the functionality needed, and
then re-evaluate to figure out a design.  Its a more iterative
approach.  Write a little code. Refactor.  Hopefully a good design
will emerge.  If not try something else.

### Deadline is not a Bad Word

Growing up my dad would always tell me: "There is no time", but I
didn't understand what he meant until I got a job at 15 years old.
Deadlines are part of life, and furthermore they are not bad.  A
deadline is just a constraint.  Without deadlines we developers could
work on software design forever and never actually get to
implementation!  Deadlines can actually help cure analysis paralysis
by reducing the number of options available to us.  Rewriting the
whole project in python suddenly isn't an option.  Deadlines force
value judgements to be made.

### Why the General Case Takes so Long

As you begin implementing your perfect design you may find holes.
This is one of the reasons for the shift from waterfall development to
agile (or even just shorter iterative processes).  Once your design is
implemented to 90% you are constrained with all these implementation
details.

To paraphrase Albert Einstein:
{% blockquote %}
"At design-time, design and implementation are the same.  At implementation-time, they are not."
{% endblockquote %}

The following quote is about ruby implementation, but it can be applied to any hard general case problem.

{% blockquote Charles Nutter http://blog.headius.com/2009/03/on-benchmarking.html %}
Listen, people: Ruby is hard to implement. Oh, it may look easy at a glance, and you can probably get 70, 80, or even 90% of the way pretty quickly. But there's some crazy stuff in that last 10% or 5% that totally blindsides you if you're not looking for it. An early Ruby implementation has not run that last mile of Ruby implementation, and it takes almost as much work to get there as it does to run the first 90%.
{% endblockquote %}

When he talks about getting blindsided by that last 10%, that is
potentially a missed deadline.


### Solving the Problem of Solving the General Case

  Ask yourself if you can live with a 90% solution.  Do you really need to solve the general case?  If 90% is not enough, break the general
case down into many smaller pieces of functionality and many smaller
deadlines.  You may still run into missed deadlines and problems, but
they will have smaller and more predictable impact.  This doesn't
really solve the overall problem of software that takes too long to
develop, but it makes the problems easier to manage.
