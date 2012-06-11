---
layout: post
title: "Sometimes Side Projects Fail"
date: 2011-12-09 16:44:56
comments: true
categories: ["rants","programming"]
---

<img src="/images/side-projects-fail.jpg" alt="Sometimes Side Projects Fail" class="center"/>

I've worked on a few side projects over the years.  Sometimes they've
turned out well, and other times I stopped working on them.  How do
you know when it's time to throw in the towel and when it's time to
push through?

<!--more-->

Roughly a year ago a friend and I were working on a bill splitting
system.  It was supposed to solve the problem of splitting bills
between friends.  More specifically, splitting regularly occuring or
one time expenses between roommates.  Rather than worrying about
having cash, or writing a check and waiting for it to cash, we built a
system which piggybacked off of paypal's API to send bill and payment
notifications via email, which would generate a web checkout page
where the debt could be paid online through paypal.

See how long the previous sentence is?  Sounds too complicated already
and I'm the one who built it. The eventual idea was that we would wrap
this in a native client wrapper, so that if you're out to dinner with
your friends you don't have to worry about splitting the bill.  One
person will pick up the entire bill, split it and send bill
notifications via email to all the other people.  Then the others pull
out their phones and enter their paypal accounts and send payment for
their portion of the bill.  The bill can be settled on the spot.

### Not Every Idea is a Hit

In a perfect world every side-project would be a hit that turns into
a business that generates lots of profit for little work.  In practice
this actually can be quite difficult to pull off.  Furthermore
sometimes those big hits aren't actually big hits when they start.  It
make take a couple of years of work to pull.  But how do you know if
your idea is taking a couple of years to get started or simply not
good at all?  Nobody wants to be a quitter, and worse nobody wants to
quit a good idea that ends up making someone else rich.  But there's
also more to life than money.

After working on this idea for a few hours a week for a couple months
we eventually decided to scrap it.  There really didn't seem to be a simple
way to make money with this idea.  It may have been a useful service,
but there are already similar free services out there for this.  Over
the years, I've grown to have an affinity for ideas that have
monetization strategies that are simple to understand.  In my
experience, the more complicated it is, the less the likelyhood of
actually making money.

Most importantly I wasn't particularly passionate about the idea, and
I didn't like the idea of piggybacking off of Paypal because of their
horrible customer service (I recently had my funds availability
delayed for 3 weeks with no explanation, and I've had an account for 7
years and an ebay account with perfect feedback).  But using another
online payment system made the idea less useful because other peer to
peer payment systems simply aren't as ubiquitous.

### Benefits of Side Projects

Often the benefits are not monetary in nature.  In the case of this
bill splitting website, I used it at the time to keep up to date with
rails 3 and refresh my skills a little bit.  I was using Merb for most
projects at work at the time. Furthermore, working on small side
projects now and then keeps you familiar with how to start a project
from scratch and increases the breadth of your knowledge.  If its a
small project with just one person working on it, you have to be the
one to do everything (or at least hire the contractors that will do
the part outside your expertise, which is a skill in itself).

The most important thing is to simplify your idea.  Then build the
simplest thing that could possibly work.  Then keep at it and don't be
afraid to re-evaluate your idea.  It doesn't make you a quitter to throw out a project that no longer seems reasonable.

Check out an older post of mine about [side projects](/blog/importance-of-side-projects/).

