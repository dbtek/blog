---
layout: post
title: "Start Testing with Angular JS"
description: "Scaffolding Angular JS apps and test automation with karma, grunt."
lang: en
category: "App Development"
tags: [angular, yeoman, grunt, testing]
---
{% include JB/setup %}

As widely known, Angular JS is saving our lives with its practical and yet powerful functionalities. And, test driven development with Angular JS is a dream already came true. Angular JS with its sophisticated dependency injection, module structure and plain old Javascript object models is so easy to code, maintain and test.

###Let's Get Started

[Yeoman](http://yeoman.io) is an workflow scaffolder to create webapps with well known best practices. Yeoman works with generators published out there via [npm](https://www.npmjs.org/search?q=yeoman+generator).

Yeoman is needed to scaffold angular app ready to testing. To install Yeoman run commands below (after installing [node](nodejs.org) and npm)

```bash
$ npm install -g yeoman
```

####Scaffold Angular JS App

First let's install Yeoman Angular generator.
```bash
npm install -g yeoman-angular
```

Then create a project directory in your workspace
```bash
mkdir angular-karma
```

Inside the created directory scaffold your app
```bash
yo angular
```

Following the instructions you can choose additional libraries such as Bootstrap, angular-route or angular-sanitize modules and sass. This command generates the required source files, creates a grunt file with tasks; installs required node modules, runs tasks, installs bower components and makes app ready.

####Tests
There is a test file for the Main controller under `test/spec` directory. This test ensures a model in the controller, *awesomeThings* has 3 objects.


