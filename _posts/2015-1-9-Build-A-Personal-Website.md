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
	color: white;
}
```

**background** and **color** are two of the many CSS properties that exist for styling html. Check out [W3Schools](http://www.w3.org/css) for more information. 

Now we need to attach our styling to our html. We will do this with a "<link/>" tag. In **index.html** replace the "links go here" comment with the following line:

```HTML
<link rel="stylesheet" type="text/css" href="style.css"/>
```

**index.html** should now look like this:

```HTML
<head>
	<link rel="stylesheet" type="text/css" href="style.css"/>
</head>
<body>
	<h1>
		Welcome to my corner of the Web!
	</h1>
</body>
```

This will connect our styling to our html. Save the files and view them again in your browser. You should see that our styling has been applied to the html.

Let's add some more styling to our html and review what each properties does. Add the following lines of code to **style.css**:

```CSS
body {
	/*makes the page orange*/
	background: orange;
}

h1 {
	/*makes the text white*/
	color: white;
	text-align: center;
	margin-top: 30px;
}
```

We use CSS to attach styling to html elements. In the file above you can see the keyword **body** with brackets and then listed properties. That code attaches those styling properties to any html tag **body**. An important thing to note is that children elements(elements withing elements like the **h1**) inherit styling from their parent elements. 

##CSS ids and classes

One of the simplest ways to style your html is with **CSS ids and classes**. Before we saw how to style html tags, but what if we want to style unique elements in their own way? We use **ids** to attach styling to unique elements in html. A specific id should only be **unique** and only used once. If you are attaching similar styling to many elements, you should use a class. Classes allow you to write one class containing your styling and apply that class multiple elements rather than writing all the styling for each element.

**How to specify Ids and Classes in CSS**

```CSS
/* id syntax */
#myElt {
	/* style */
}

/* class syntax */
.myClass {
	/* style */
}

```

**How to give html elements Ids and Classes**

```HTML
<body>
	<div id="myElt">
		This is Unique
	</div>
	<button class="myClass">This is Repeated</button>
	<button class="myClass">Yes you're right</button>
	<button class="myClass">Well now I know!</button>
	<button class="myClass">Time to continue</button>
</body>
```

Let's re-factor our code to use ids were appropriate:

**style.css**

```CSS
body {
	/*makes the page orange*/
	background: orange;
}

#welcome {
	/*makes the text white*/
	color: white;
	text-align: center;
	margin-top: 30px;
}
```

**index.html**

```HTML
<head>
	<link rel="stylesheet" type="text/css" href="style.css"/>
</head>
<body>
	<h1 id="welcome">
		Welcome to my corner of the Web!
	</h1>
</body>
```

##What is a git repository?

I'm glad you asked. Our website is going to be made of up one or more files containing HTML, CSS, and JavaScript. **Git**, is in charge of managing all the code that we've written and moving it from place to place quickly and cleanly. Think of it sort of as a wrapping around all the files in a folder. It keeps track of changes, creations, and deletions of files and allows you to version your website.  