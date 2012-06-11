---
layout: post
title: "Verify your Assumptions"
date: 2011-12-07 09:41
comments: true
categories: []
---

<img src="/images/ram.jpg" class ="center"/>

Always verify your assumptions.  It will save you time and headache.
I'll explain now.

<!--more-->

### Building a PC

I recently built a PC from parts I bought online.  It had been 5 years
since I've built a PC at the time so I'd forgotten my good habits.  I
put everything together: RAM, CPU, HDD, GPU, motherboard etc...  and
it booted up and POST'ed no problems.  I thought I was good to go at
this point.  I managed to install windows and a bunch of drivers, but
then I started getting random freeze ups.

### Troubleshooting

I thought perhaps it was one of the drivers or something specific to
windows 7 (this is a gaming box, not for work).  So I did a little
digging and actually ended up reinstalling windows bare to rule out
any driver issues.  Long story short, while the box would work fine
for about 10 minutes, shortly thereafter the box would freeze up.

It was at this point that I decided to get a boot CD with some
troubleshooting utilities.  I chose
[Ultimate Boot CD](http://www.ultimatebootcd.com/) because it's free
and has almost everything you could need for diagnostics.

### Testing

For whatever reason, when I built the PC I did it wrong.  I skipped
the testing phase.  I didn't test first.  So now I was in a situation
where I was digging through everything to get to the root of the
problem (and hopefully there's only one!).  First I tested the HDD
using HDAT2.  Many hours later, it came back clean.  Then I tested
using Memtest86.  Within a couple of minutes it detected an error.  So
I pulled the 2 RAM sticks, and tested each individually, and
determined that I had 1 bad stick of RAM.

### The Point is

If I had built my system right: plug in as little as possible to get
it to boot and run diagnostics before installing software, I would
have found my problem much faster and saved hours of time.  My problem
here was that I assumed my RAM was good.  So even when you're not
programming it's important to verify your assumptions and don't forget to test.
