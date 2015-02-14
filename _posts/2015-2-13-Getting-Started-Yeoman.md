---
layout: post
title: Less Boilerplate more awesome with Yeoman
tags:
- code
---

**Too many precious hours have been spent struggling to set up something simple.** With the tools available to web developers today, building something from scratch is almost stubborn. Instead of building your idea from scratch, you can save a **large** amount of time and mold an already well made app into your idea.

**Yeoman** does just this. It builds a well made application for you to mold into the app that you want. Let's go through how easy it is to setup a simple angular application. Yeoman actually does way more than just set up an app. When you finish this tutorial you will have a very stable development environment complete with automated server reloads and testing already setup. Pretty sweet right?

##Prerequisits

You will need to have **Node.js** and **NPM** installed in order to get Yeoman. If you haven't installed them yet, get them [here](http://nodejs.org/download).

We'll use these to serve our app, run our tasks, and manage packages.

##Yeoman

![Yeoman](http://juristr.com/blog/assets/imgs/node-grunt-yeoman/yeoman-logo.png)

Yeoman helps us build a stock application. It will give us a simple skeleton from which we can build our app. As mentioned earlier above yeoman will set us up with a nice development environment with automated tasks and included tests.

Yeoman Generators are the blueprints for our skeleton apps that we will make. There are very many and are all open source. We will use one made by the Yeoman team themselves. We'll learn more about generators later on.

##Grunt

![Grunt](http://juristr.com/blog/assets/imgs/node-grunt-yeoman/grunt-logo.jpeg)

Grunt is a task-runner. It will help speed up our workflow by automatically compiling assets, restarting our server, and doing whatever else you tell it to.

There are alternatives to Grunt out there, **Gulp** being possibly the most popular. Both have advantages and do very similar things. For this tutorial we will use Grunt, but know that Gulp exists.

##Bower

![Bower](http://juristr.com/blog/assets/imgs/node-grunt-yeoman/bower-logo.png)

Bower will be our front-end package manager. It makes loading dependencies like angular, jQuery, and many other common libraries and frameworks, easy and hassle free.

Bower eliminates the need to have script tags all over your html in development. Also, from the designer in me, I love that bird icon.

##Getting Started

Install all three of the packages above with the following line:

```
$ npm install -g yo bower grunt
```

The `-g` will install these packages globally so you can use them from anywhere.

##Generators

Yeoman generators are the different app skeletons that can be setup with Yeoman. There are a ton of awesome ones out there and you can even make your own. The one we will be using is an **Official Yeoman Generator** so it was made by the Yeoman team.

Check out the popular generators on the [Yeoman Generator Page](http://yeoman.io/generators)

**Our generator** will give us a simple AngularJS application with that uses Grunt and Bower. Install globally with the following command.

```
$ npm install -g generator-angular
```

##Building our App

Now that we have all our dependencies installed we're ready to whip up a web app! Run the following command to instruct Yeoman to build our app using our angular generator. Be sure to name your app how you like.

```
$ yo angular <app_name>
```

First you will be asked if you would like to use Sass or Compass Code. If you are familiar with them then by all means go ahead. If not it's probably best to say no. There are other prompts for Bootstrap and other things, do what you want with these but know that some of these add-ons come with certain dependencies which you may not have.

Once you power through these initial questions Yeoman should be hard at work cranking out your application and environment!

##Viewing our App

I am anxious to see what Yeoman created! Once it is done blasting your terminal with info we use the `serve` task in grunt to view our new app.

First we have to build our app using **Grunt**. Use the following command to compile your assets and build your app.

```
$ grunt
```

To get a quick view of what Yeoman made run the next command. This will set up a quick server to serve your angular app and even open a browser tab to it!

```
$ grunt serve
```

##Exploring our App

As you saw above, we generated a pretty basic application. Now check out the code behind by opening up our app in your IDE or text editor of choice.

Another great thing about Yeoman and great generators is that you are started off with a great example of project structure and code style. You should be able to keep a pretty clean app by sticking to the pre-set style as you add more code and functionality.
