---
layout: post
title: Host your side project for free
---

In this post I explain how to host your side project on Heroku for free. There are some limits of course. I'm assuming your side project is written in Ruby (RACK compatible), Node.js, or Clojure. I'm assuming you're using git for version control (heroku uses git push for deploys). I'll also discuss storage limitations (database, web assets, etc).

Looking for inspiration for a side project? [Read my post about side projects](http://rawsyntax.com/post/5982784556/importance-of-side-projects)

## Sign up for Heroku

{% img http://media.tumblr.com/tumblr_lpp3jgSnE31qfdxjm.png %}

## Create a Project on Heroku

First install the heroku gem.

{% gist 0c11cc5ab4b40d165ab9 %}

Then create a project with the cedar stack on heroku.

{% gist 8d1ded8c7d4172e1d17c %}

Log in to Heroku and check out your app.

{% img http://media.tumblr.com/tumblr_lpp485CMTR1qfdxjm.png %}

You should see something similar to the above. At this point you've created your project on heroku. Awesome, but there's still more to do.

## Deploy your project to heroku

Note the git repository listed on your project's heroku page. Add it as a remote on your project with:

{% gist 961c4ed5eb4d0a21fb6b %}

But most likely you will get a slew of errors. What about database setup and all the other steps that go with production application setup?

## Set your project up for Heroku

Here's where Heroku's Addon system comes in. Basically, you're going to replace your database server, frontend load balancing / reverse proxy, and daemon processes / cron jobs with Heroku Addons. This is a subject for another post, but I'll go over what my standard stack is.

Furthermore, Heroku has good documentation about their platform and Addons [here](http://devcenter.heroku.com/)

## My standard stack

Lately I've been using Rails 3, Mongoid for models, Haml and Sass for views, and sendgrid for sending emails.

On Heroku I'll install the following free Addons:

* Sendgrid for sending and receiving emails (200 a day free)
* MongoLab for a free mongodb instance (240mb)
* Advanced Logging
* Custom Domain (for my own .com instead of a heroku subdomain)

Note that your app slug (application files deployed to heroku) is limited to 100mb, but I have yet to run anywhere close to that. My side projects generally run around 10mb. Heroku recommends you use an asset host for any js/css/images.

Heroku, with these addons is enough to get any side project off the ground. And there's always the option to scale up with Heroku, or move it to your  paid host once it starts to grow.
