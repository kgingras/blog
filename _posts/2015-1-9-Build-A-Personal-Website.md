---
layout: post
title: Build and Push A Personal Website
tags:
- code
---

**If you're just getting into developing this post is made for you**. By the end of this tutorial you will have a personal website up on the web for all to see! We will be using HTML, CSS, jQuery, and Github to make this happen. If you don't have any experience with any of these, don't worry we'll go through them. 

##How it will work

We'll make our website locally, which means we will be creating our website first on our computer with no connection to the Internet needed. We will write some code that will be interpreted by a web browser as a web-page. Then, we will send that code to a server which will make our site live and viewable on the web. To send our code to the server and make updates we will be using something called **Git**. We'll learn about this later, let's start building our site!

##Development Environment

Your development environment is basically what tools do you use to make it easier to develop. Building a webpage is very simple so we don't need any heavy programs to help us because we will just be editing documents and running commands. First we will download a simple editor called **Sublime Text**.

##Sublime Text Editor

Firstly, go to [Sublime.com](http://sublimetext.com) and download the latest version of sublime text. If you already have it installed you can skip this section.

Because we will be working with HTML, CSS, and JavaScript which are **Interpreted Languages**, we simply edit them as as we would a word document. That being said, you could build your website using Notepad, but text editors like Sublime are much smarter than Notepad. Sublime makes it much easier to develop with things like inteli-sense and language highlighting. Basically it will help you develop better and faster.

##Basic HTML

Create a folder called **/website** to put all your files in. It is important that all these files be together later in the tutorial when we want to make our site live.

Inside **/website** create a file called **index.html**. This will be the basis our website, an html document that people will see when visiting your site.

Open up the **index.html** in Sublime Text. Now add the following code to the document and save it:

```html
<h1>
	Welcome to my corner of the Web!
</h1>
```

Once you've done this go back to your folder and right click on **index.html**. Now click, open with -> Chrome, or whatever browser you use. You should see your **index.html** file being interpreted by your browser into that glorious one line times new roman greeting. Good work, lets keep moving.

##Styling With CSS

The web has become a beautiful place and sadly no one wants to see plain html anymore so we will use something called **CSS or
Cascading Style Sheets**. CSS allows us to color, move, position, and do many things to our html. It has many properties allowing you to mask html in many ways. 

First lets update our **index.html** file to be better laid out. 

```HTML
<head>
	<--! links will go here -->
</head>
<body>
	<h1>
		Welcome to my corner of the Web!
	</h1>
</body>
```

Create a file in your **/website** folder called **style.css**. We will use this file to make our html look pretty. Add the following code to **style.css**. 

```CSS
body {
	/*makes the page orange*/
	background: orange;
}

h1 {
	/*makes the text white*/
	color:white;
}
```

**background** and **color** are two of the many CSS properties that exist for styling html. Check out [W3Schools](http://www.w3.org/css) for more information. 

##What is a git repository?

I'm glad you asked. Our website is going to be made of up one or more files containing HTML, CSS, and JavaScript. **Git**, is in charge of managing all the code that we've written and moving it from place to place quickly and cleanly. Think of it sort of as a wrapping around all the files in a folder. It keeps track of changes, creations, and deletions of files and allows you to version your website.  