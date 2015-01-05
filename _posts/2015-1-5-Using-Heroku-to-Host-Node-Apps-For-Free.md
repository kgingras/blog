---
layout: post
title: Using Heroku to Host Node Apps for Free
tags:
- code
---

Hello, in this tutorial we will go over how you can put your Node App up for the world to use for free. You will need to have a Node App ready to go if you want to have it running at the end.

##Heroku

Heroku is a **Hosting Service** thats supports many platforms of development. In this case we will be using Node.js. It is awesome for putting simple projects out there for **Free** to start, it can get pricey if you want to beef up your speed but great to start with. Here are some great features of Heroku.

*	**Free** - As we mentioned before, Heroku has a free plan which is great for poor college students like myself.

*	**Git Integration** - Heroku allows you to Deploy your Apps using Git. Push your changes up and see them in seconds. My favorite feature by far.

*	**Logging** - If something goes wrong Heroku makes it easy to find your bugs.

##Setting up Heroku Account

First head to [Heroku.com](http://Heroku.com) and create an account.

There you will install something that will allow to use **Heroku** in the command line. If you're on windows, I highly recommend using **Git Bash**. It makes a lot of things simple and easy.

Once you have installed the download. Run the following command as seen on the Heroku site.

```
$ heroku login
```

This will prompt you for your **username** and **password** for your Heroku account. Once you enter that you can move on the the real stuff.

##Setting up the Remote

If you're familiar with **Github**, a remote repository allows you move your local **Git Repository** to a remote repository the hosted somewhere on the web. This can be Github or in our case, Heroku.

Make sure you are in the directory of your Node App. Once there, run the following command to create a Heroku App in your account.

```
$ heroku create
```

This command will create a Node.js app on Heroku and a remote repository which we can now push code to. You should see a lot of Heroku dialog and the usually very tasteful name that Heroku has given your new app.

##Deploying the App

Now that we have created our remote repository, Deploying our App is easy. Run the following command to push your app to Heroku.

```
$ git push heroku master
```

Now all your code is up in your remote repository on Heroku. You have **Deployed** your Node App! Yay.

In order to ensure at least one instance of your app is up and running, run the following command.

```
$ heroku ps:scale web=1
```

Now you can open a browser tab directly to your App by running the following.

```
$ heroku open
```

##Logging

If you encounter the **Infamous Heroku Error Screen** fear not. Simply run:

```
$ heroku logs
``` 

In your terminal to get all the data about the latest crash. You will have to reset your one Dyno to get your App, back up and running.

##Name Changing

If you wish to change the name of your App from **flurishing-tides-3434** to something more simple. Just go to your account on Heroku, where you can change the names of your Apps. You're allowed up to 5 on the free plan!

##Conclusion

I hope you enjoyed this tutorial. It's a really cool service that allows developers to put there works of art up for the world to use and see. 

