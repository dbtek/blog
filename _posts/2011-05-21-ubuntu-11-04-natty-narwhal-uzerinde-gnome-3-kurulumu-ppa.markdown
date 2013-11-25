---
author: dbtek
comments: true
date: 2011-05-21 14:59:41+00:00
layout: post
slug: ubuntu-11-04-natty-narwhal-uzerinde-gnome-3-kurulumu-ppa
title: Ubuntu 11.04 (Natty Narwhal) üzerinde Gnome 3 Kurulumu (PPA)
wordpress_id: 324
categories:
- Bilişim-Teknoloji
- Linux
tags:
- gnome
- gnome3
- install
- kurulum
- narwhal
- natty
- ubuntu
- unity
---

Ubuntu 11.04'ün [Unity](http://unity.ubuntu.com/)'si ne kadar güzelse de [Gnome 3](http://gnome3.org/)'ün tadına Natty'de bakmanın bir sakıncası olmamalı. Bunun içinyapılması gereken çok da fazla bir şey yok. Gnome 3 PPA'ini yazılım kaynaklarına ekleyip dağıtım yükseltmesi yapmak gerekiyor. Şöyle ki, Terminal'de

<!-- more -->

{% highlight bash %}
$ sudo add-apt-repository ppa:gnome3-team/gnome3
$ sudo apt-get update
$ sudo apt-get dist-upgrade
$ sudo apt-get install gnome-shell
{% endhighlight  %}

komutlarını girilir. Bilgisayarı yeniden başlatıldıkttan sonra login ekranında alt kısımdaki menüden _Ubuntu GNOME Shell Desktop_ seçilerek giriş yapılır. Unity 2D Gnome 3 ile birlikte kullanılamıyor.
