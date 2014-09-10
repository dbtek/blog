---
layout: post
title: "Angular Off Canvas Menu"
category: 
tags: [angular, off, canvas, menu, ui, bootstrap, modal]
---
{% include JB/setup %}

Angular UI is a huge project providing many easy to use components with very much comfort. I personally use these modules nearly all of my Angular JS & Bootstrap projects.

One thing I suppose I needed with these super cool components was a good off-canvas side menu. There are a few solutions for that. Some of them like Snap or Sidr requires JQuery which is not cool in an Angular JS application. [Angular-Strap](http://mgcrea.github.io/angular-strap/) provides a very good aside, however you should depend on things in angular-strap to use this and I personally want to go with angular-ui instead of angular-strap.

So there were no choices left other than delivering an off-canvas menu module totally usable with angular-ui. An off-canvas menu is actually pretty same with a modal in practice. Only differences between a modal and an off-canvas menu would be the placement and the animation. So I decided to extend the modal of ui-bootstrap.

Off canvas menu should be created in controllers and should support both string contents and an html templates just like the modal. So the modal's provider is also very suitable for this purpose.

A little css hacking on modal gives us the off-canvas menu we always wanted. And modal has the windowClass option, awesome! 

```js
...
var modalInstance = $modal.open({
  windowClass: 'ng-aside'
});
```

This creates a modal window with class `ng-aside`. All to be done is hacking the modal with some css to make it look like a menu. However if we want a menu we would want it to be configurable like place it left or right. So I have released this [angular-aside](https://github.com/dbtek/angular-aside) module which basically does it by extending `$modal` provider with a factory named `$aside` (thanks to angular-strap for the name) supporting all the configuration that modal provides. Additionally there is the `placement` configuration to set menu location left or right. It also includes animations provided by the awesome [animate.css](http://daneden.github.io/animate.css/).

Here is an example usage: 

```js
angular.module('myApp', ['ui.bootstrap', 'ngAside'])
  .controller('MyController', function($scope, $aside) {
    var asideInstance = $aside.open({
      templateUrl: 'aside.html',
      controller: 'AsideCtrl',
      placement: 'left',
      size: 'lg'
    });
  });
```

###Live Demo

<iframe style="border: 0; width: 100%; height: 300px" allowfullscreen="allowfullscreen" src="http://embed.plnkr.co/w8Clzab6jJf6fPMHEXpP/preview">
  Loading plunk...
</iframe>

Easy, right? Angular-aside lives right [here](https://github.com/dbtek/angular-aside) at Github!