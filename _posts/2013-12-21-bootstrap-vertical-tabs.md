---
layout: post
title: "Bootstrap Vertical Tabs"
description: "Missing vertical tabs component for Bootstrap 3"
lang: en
categories:
- Projects
tags: [bootstrap, vertical, tabs, component, missing]
project: {
            github: 'https://github.com/dbtek/bootstrap-vertical-tabs',
            license: { name: 'MIT', url: 'http://opensource.org/licenses/MIT' }
        }
---
{% include JB/setup %}

I personally use Bootstrap a lot on my projects. As known Bootstrap removed vertical tabs with 3rd version. I think they were pretty handy. Especially for navigation inside a content.

So I have managed to use vertical tabs with some additions and made this project named, *Bootstrap Vertical Tabs*.

It's very practical and pretty much like bs3 styled.

### Usage

* [Download](https://github.com/dbtek/bootstrap-vertical-tabs/archive/master.zip) the latest css.
* Include in your html.
{% highlight html %}
<link rel="stylesheet" href="bootstrap.vertical-tabs.css">
{% endhighlight %}

* Use it.

{% highlight html %}
<div class="col-xs-3"> <!-- required for floating -->
    <!-- Nav tabs -->
    <ul class="nav nav-tabs tabs-left">
      <li class="active"><a href="#home" data-toggle="tab">Home</a></li>
      <li><a href="#profile" data-toggle="tab">Profile</a></li>
      <li><a href="#messages" data-toggle="tab">Messages</a></li>
      <li><a href="#settings" data-toggle="tab">Settings</a></li>
    </ul>
</div>

<div class="col-xs-9">
    <!-- Tab panes -->
    <div class="tab-content">
      <div class="tab-pane active" id="home">Home Tab.</div>
      <div class="tab-pane" id="profile">Profile Tab.</div>
      <div class="tab-pane" id="messages">Messages Tab.</div>
      <div class="tab-pane" id="settings">Settings Tab.</div>
    </div>
</div>
{% endhighlight %}

For more, please visit the project page: [http://dbtek.github.io/bootstrap-vertical-tabs](http://dbtek.github.io/bootstrap-vertical-tabs)
