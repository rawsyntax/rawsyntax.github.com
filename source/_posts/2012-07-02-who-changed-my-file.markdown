---
layout: post
title: "Who Changed my File"
date: 2012-07-02 18:27
comments: true
categories: ["programming"]
---

I was troubleshooting slow page loads on a server running rails
recently.  I noticed that DNS was actually causing an occasional
problem with pageloads.  For whatever reason my `/etc/resolv.conf`
would get overwritten every once in a while with slow / unresponsive
DNS servers.  I had manually set them to `8.8.8.8` and `8.8.4.4`, but
to my suprise the file had been changed.

I started digging and checking the usual suspects that might alter
that file (`dhclient`, `resolvconf` ...).  I didn't find the problem.
This is where `auditd` comes in handy.  Its a daemon that can be setup
to watch a file and log what program changed it.

I installed `auditd` and set it up to watch `/etc/resolv.conf` and log
any write or append actions (as I don't care about who reads it):

`auditctl -w /etc/resolv.conf -p wa -k resolvconf`

`-k` here is simply the key by which you can search the audit logs.  I edited the file a few times to test auditd and searched its logs:

`ausearch -f /etc/resolv.conf `

It logs all kinds of info.  user id, command run, working directory.
I'm blogging it here mostly so don't forget about it.
