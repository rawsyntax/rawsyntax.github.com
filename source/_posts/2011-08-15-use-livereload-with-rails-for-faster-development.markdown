---
layout: post
title: Use LiveReload with Rails for faster development
categories: ["ruby", "code"]
alias: [/post/8958871921/use-livereload-with-rails-for-faster-development, /post/8958871921]
---

LiveReload applies CSS/JS changes to Safari or Chrome without
reloading the page, and automatically reloads when the html changes.
Let that soak in for a minute. In this post I'll go over how to get it
installed and working on your Rails projects.

<!--more-->

The installation process has two steps. First we install a browser extension that listens for livereload events. Then we use guard to listen for  system events and send information to the browser.

First install the livereload addon for [chrome](https://chrome.google.com/webstore/detail/jnihajbhpnppcggbcgedagnkighmdlei) or [safari](https://github.com/downloads/mockko/livereload/LiveReload-1.6.2.safariextz).

In your rails project gemfile add

    gem 'rb-fsevent'
    gem 'guard-livereload'

Run

    bundle install
Then run

    guard init livereload && guard

To setup guard for livereload and start monitoring for file system events. The last step is to activate the browser extension. You will need to click the LiveReload button:

{% img http://media.tumblr.com/tumblr_lpzehwqgO41qfdxjm.png %}

Now when you change a file in your view, Safari / Chrome will load the new content automatically.

## Notes on RubyCocoa

The notes on the [livereload repo](https://github.com/mockko/livereload) are a little confusing. Livereload can also work via RubyCocoa (instead of guard- livereload). If you're running ruby 1.9.2 you cannot install RubyCocoa on it. RubyCocoa is not 1.9.x compatible. So I opt to use the browser extension and guard.

More info [here](http://livereload.com/)
