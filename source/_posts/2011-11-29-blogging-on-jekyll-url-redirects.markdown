---
layout: post
title: "Blogging on Jekyll: URL Redirects"
date: 2011-11-29 14:32
comments: true
categories: ["programming", "blogging"]
alias: [/blog/blogging-on-redirects]
---

About a month ago I migrated my blog from Tumblr to Octopress hosted
on github-pages.  I migrated because of Tumblr's slow page loads and
frequent downtime.  I picked Octopress because it is built on top of
Jekyll, and it comes with a reasonable default stylesheet.  Jekyll is
a static site generator, which ensures I can deploy my blog on any old
server in the future, and continue to use these same old tools
(because I have them, rather than tumblr having them).

<!--more-->

### Migrating broke my URL Structure

<img src="/images/urls_not_found.png" class ="center"/>

Running my site through Google's Webmaster Tools showed that many sites are still linking to my old Tumblr blogpost urls.  Tumblr's url structure is another reason I migrated away from it.  I should be in full control of the urls on my blog.  Never the less, I need to support redirects from the old URLs to my new URL structure `/blog/:post_title`.

However Jekyll is just a static site, so there's no ruby server to handle redirects.  Other Jekyll users deploy to Heroku and use a small Sinatra app to handle redirects, but I feel like that is complicating my simple setup.  If I were on a regular server I could setup an `.htaccess` file to handle the redirects, but github-pages does not support `.htaccess`.

###  Jekyll Plugins to the Rescue

One of the great things about Jekyll is its simple plugin system.  On
[Jekyll's Wiki](https://github.com/mojombo/jekyll/wiki/Plugins) I
found the
[Alias Generator](https://github.com/tsmango/jekyll_alias_generator).
It allows you to specify aliases on a per blogpost basis, in the YAML
front matter.

This post's YAML is:

    ---
    layout: post
    title: "Blogging on Jekyll: URL Redirects"
    date: 2011-11-29 14:32
    comments: true
    categories: ["programming", "blogging"]
    alias: [/blog/blogging-on-redirects]
    ---

Now when I `rake generate` my site, the Alias Generator will create
another static html file for this post at
`/blog/blogging-on-redirects/index.html`:

    <!DOCTYPE html>
    <html>
    <head>
    <meta http-equiv="content-type" content="text/html; charset=utf-8" />
    <meta http-equiv="refresh" content="0;url=/blog/blogging-on-jekyll-url-redirects/" />
    </head>
    </html>

Which will redirect here. Try it: [/blog/blogging-on-redirects](/blog/blogging-on-redirects)

It was almost that simple.  The Alias Generator actually broke when I
provided some of my old Tumblr urls. However, I
[forked it here](https://github.com/rawsyntax/jekyll_alias_generator)
and fixed it so it handles nested aliases properly now.  I also opened
a [pull request](https://github.com/tsmango/jekyll_alias_generator/pull/1) to the owner to get this change merged in.

### Jekyll's Strengths

That experience is Jekyll's strength as a blogging platform.  The
output is so simple any web server can serve it so it doesn't matter
where you deploy to.  Its generation system is open source, hackable,
and has a great plugin system.

But most importantly, even if the Jekyll project implodes tomorrow.  I
still have all my blog's content versioned, and have all the tools
necessary to maintain my blog.  I am not relying on a hosted service
to back up my blog's content, or maintain the tools I edit it with.

### Try Octopress

If you haven't tried [Octopress](http://octopress.org) yet, I highly
recommend it.  It's Jekyll based, but it has a decent default
stylesheet, so it's very easy to install and immediately start
blogging.  No programming or tweaking CSS to get in the way of writing content.
