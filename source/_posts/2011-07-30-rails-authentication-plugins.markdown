---
layout: post
title: Rails Authentication Plugins
alias: [/post/8257723163/rails-authentication-plugins, /post/8257723163]
---

Considering which authentication plugin to use for rails? I have some recommendations.

## Devise

Devise is a full featured authentication plugin. Featuring, remember me, forgot password, last seen timestamps, email confirmation, lockouts, and a slew of other features. They have pretty much anything you could ask for.

Devise supports activerecord and mongoid. I used it recently on a mongoid based rails 3 project. It worked wonderfully. I’ll post a code example of how I did it, in the next few weeks.

Check out their very helpful [wiki](https://github.com/plataformatec/devise/wiki/_pages), and their [long list of extensions](https://github.com/plataformatec/devise/wiki/Extensions).

## Warden

Devise is actually built on top of warden. And warden is descendant from merb-auth [(merb)](http://merbivore.com). So, if you’re like me and quite familiar with merb-auth and it’s flexibility, you’ll feel right at home with warden. I use warden when I need just the basics, login / logout / signup. Also, if you happen to be doing some custom work when logging in, such as interfacing with an API or another system, warden is built to handle it.

See Mike Thomas’ post about [getting up and running with rails and warden](http://finite.posterous.com/how-to-use-warden-authentication-with-rails-3)

[check out the code in github](https://github.com/hassox/warden)

[and the rails plugin](https://github.com/hassox/rails_warden)

## Roll your own

Some people prefer to write their own authentication system. Personally, I avoid reinventing the wheel when flexible solutions like warden and devise exist. However, there are some railscasts covering this topic in detail, if you’re interested to see how authentication works.

[railscasts: authentication from scratch](http://railscasts.com/episodes/250-authentication-from-scratch)

[railscasts: rails 3.1 authentication](http://railscasts.com/episodes/270-authentication-in-rails-3-1)

## Recommendations

Use devise if you’re running a standard rails stack with activerecord or mongoid (or couch or datamapper if you try their extensions).

If you need to do some particularly strange things with authentication, I’d recommend warden. It’ll also work with any rack compatible web app (sinatra, and others).

Don’t bother rolling your own, warden and devise do a fine (and flexible) job, and there’s plenty of other authentication plugins not mentioned here.

