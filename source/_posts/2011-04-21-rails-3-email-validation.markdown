---
layout: post
title: Rails 3 Email Validation
categories: ["ruby", "code"]
alias: [/post/4807844270/rails-3-email-validation, /post/4807844270]
---

Most email validation I've encountered goes bananas with regards to regexes. The programmer tries to strictly adhere to the spec ([rfc 822](http://www.ietf.org/rfc/rfc0822.txt)) in a regex. Not only is this task difficult and error prone, but there are functional email addresses out there that do not conform to the spec. Not to mention the resulting regex often looks like [this](http://www.ex-parrot.com/pdw/Mail-RFC822-Address.html).

When I do email validation I use a simple regex:

{% gist 934791 %}
Which I took from the [Devise](http://github.com/platformatec/devise) codebase. It means:

* begins with one or more word characters, period, percent, plus, or dashes
* then one at symbol
* then one or more word characters, dashes, and then a period
* ends with 2 or more word characters
* case-insensitive

This regex ensures a reasonably close to valid email address, without enumerating and worrying about .com vs .co.uk vs .musem and a host of other issues.

At this point, I have the application send an email to the address, and require the user to click a confirmation link. That's good enough, and very simple to implement.

[Try this regex out on Rubular](http://rubular.com/r/YTzbCkatJy) it's an interactive web based ruby regex engine.

