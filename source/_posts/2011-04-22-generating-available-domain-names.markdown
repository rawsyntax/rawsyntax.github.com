---
layout: post
title: Generating Available Domain Names
categories: ["code", "ruby"]
---

It's a ruby script that loads a dictionary of common words, restricts word length, combines two that start with the same letter, and issues a whois query to check if it's available. Feel free to tweak it to your own needs. It also has some sleep calls to avoid flooding the whois server. Let it run for a couple days, see what comes out.

I actually generated [rawsyntax.com](http://rawsyntax.com) using this script.

{% gist 1360029 %}
