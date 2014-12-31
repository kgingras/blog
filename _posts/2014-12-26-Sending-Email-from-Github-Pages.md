---
layout: post
title: Sending Emails from Github Pages
tags: 
  - code
---
As I was setting up my personal website with Github Pages (which is awesome), I ran into the issue of creating a contact form that I could receive emails from. Before, I used a service set up by umich, but it became a bit hard to work with and as you may know, Github Pages does not provide any support for server side scripting ie. PHP or Node.js.

After searching far and wide, I came across [this](http://sebastien.saunier.me/blog/2014/04/15/you-do-not-need-a-database-for-your-contact-form.html). An awesome blog post about [formspree.io](formspree.io), a free email service that lets you build simple forms to send to a single address.

[formspree.io](formspree.io) makes it incredibly easy to allow your static Github Pages to send emails to you. As seen on their site, just a few lines of code is all it takes.

```javascript
$.ajax({
  url: "http://formspree.io/email@address",
  method: 'POST',
  data: $('#myform').serialize(),
  dataType: "json",
  beforeSend: function() {
    //sending message
  },
  success: function(data) {
    //succes message
  },
  error: function(err) {
    //error message
  }
});
```

Along with the code above, I was using an invisible form and updating values with jQuery. In general, this is a very nice solution to this issue.

All you have to do is register your email with [formspree.io](formspree.io) and they'll do all the work! With up to 1000 free emails per week, it is an awesome free service that I imagine will become very popular? idk we'll see.

