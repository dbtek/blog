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

[Yeoman](http://yeoman.io) is a workflow scaffolder to create webapps with well known best practices. Yeoman works with generators published out there via [npm](https://www.npmjs.org/search?q=yeoman+generator).

Yeoman makes easy creating an angular app ready to testing by scaffolding via generators. To install Yeoman run the command below (after installing [node](http://nodejs.org) and npm)

```bash
$ npm install -g yeoman
```

####Scaffold Angular JS App

First let's install yeoman-angular generator.
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
There is a test file for the Main controller under `test/spec` directory. This test ensures a model in the controller, `awesomeThings` has 3 objects.

To run written tests under `test` directory, run `grunt test` command. This command runs tests in your app through karma with Jasmine. You probably will need to launch a browser and visit karma server most likely running on `localhost:8080` manually. This process can also be automated by installing a karma browser launcher. To install a launcher you can run one of these commands:

```bash
$ npm install karma-firefox-launcher --save
$ npm install karma-chrome-launcher --save
```
####Further
`yeoman-angular` generator promises much more than these. There are plenty of [sub-generators](https://github.com/yeoman/generator-angular#generators) available within this generator.

For example, running `yo angular:route user` generates a controller on `/app/controllers/main.js` with name `MainCtrl`, a view under `/app/views/user.html` and a unit test on `/test/spec/controllers/main.js`. Also adds route configurations to `/app/scripts/app.js`.

You can visit [project page](https://github.com/yeoman/generator-angular#angularjs-generator-) for documentation.