---
layout: post
title: Less Boilerplate more awesome with Yeoman
tags:
- code
---

**Too many precious hours have been spent struggling to set up something simple.** With the tools available to web developers today, building something from scratch is almost stubborn. Instead of building your idea from scratch, you can save a **large** amount of time and mold an already well made app into your idea.

**Yeoman** does just this. It builds a well made application for you to mold into the app that you want. Let's go through how easy it is to setup a simple angular application.

##Prerequisits

You will need to have **Node.js** and **NPM** installed in order to get Yeoman. If you haven't installed them yet, click [here](http://nodejs.org/download).

##Getting Started

We will use npm to install all the things listed below:

###Yeoman

!(Yeoman)[http://juristr.com/blog/assets/imgs/node-grunt-yeoman/yeoman-logo.jpeg]

Yeoman helps us build a stock application. It will give us a simple skeleton from which we can build our app.

###Grunt

!(Grunt)[http://juristr.com/blog/assets/imgs/node-grunt-yeoman/grunt-logo.jpeg]

Grunt is a task-runner. It will help speed up development workflow by automatically compiling assets, restarting our server, and doing whatever else you tell it to.

###Bower

![Bower](http://juristr.com/blog/assets/imgs/node-grunt-yeoman/bower-logo.png)

Bower will be our front-end package manager. It makes loading dependencies like angular, jQuery, and many other common libraries and frameworks, easy and hassle free.

```
npm install -g yo bower grunt
```

The `-g` will install these packages globally so you can use them from anywhere.

##Generators

Yeoman generators are the different app skeletons that can be setup with Yeoman. There are a ton of awesome ones out there and you can even make your own. The one we will be using is an **Official Yeoman Generator** so it was made by the Yeoman team.

Let's install our angular generator

```
npm install angular
