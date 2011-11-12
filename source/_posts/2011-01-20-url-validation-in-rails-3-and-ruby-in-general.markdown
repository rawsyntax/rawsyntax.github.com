---
layout: post
title: URL Validation in Rails 3 (and ruby in general)
categories: ["ruby", "code"]
---

I've seen some approaches, most notably [here on igvita](http://www.igvita.com/2006/09/07/validating-url-in-ruby-on-rails/). Though the reference on igvita is quite dated (2006 ??? being more or less the beginning of the epoch in rails-years), I've seen plenty of code using the validate-a-uri-by-regex approach.

It doesn't work and pretty much always ends up excluding valid urls. This is why I prefer to use the parsing approach. If the url can be parsed, and the scheme seems reasonably valid, good enough.

## An Interesting URL Problem

Recently I ran into a situation where I needed to be able to validate and handle unicode / internationalized links. One such link would be [the russian tld registrar кц.рф](http://%D0%BA%D1%86.%D1%80%D1%84). The typical approach of parsing with URI fails below

{% gist 789195 %}

## The Solution

At this point, I happened to remember there is another library for parsing URIs. It's called [Addressable::URI](https://github.com/sporkmonger/addressable). Its aim is to be a full replacement of the ruby standard library's URI module.

More importantly, it successfully parses unicode urls.
{% gist 789235 %}

Here's how I do URL validation in rails 3, using ActiveModel and Addressable::URI.
{% gist 789162 %}
