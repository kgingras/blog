---
layout: post
title: Passport Facebook Profile Picture Workaround
tags:
- code
---

I recently started using **Passport** for Node authentication. It is incredible and extremely useful. Check out **Scotch.io**'s awesome tutorial on authentication with Node.

Anyway, I ran into some issues grabbing certain Facebook fields from passport-Facebook, namely profile pictures. I believe these issues were caused by recent changes to the facebok API. Normally in passport-Facebook you can just inject **picture** and **photos** as profile fields shown below.

```javascript
app.get('/auth/facebook', passport.authenticate('facebook', {
    scope : ['email'],
    profileFields : ['id', 'displayName', 'emails','photos', 'picture']
}));
```

This was causing issues as photos would not be returned nor would picture. A couple suggestions I found online used the Graph API but required the user's name which was also not returning.

The solution I am currently using turned out to be much simpler than anything found elsewhere. After researching the new changes to the Graph API, I found that you can get a users profile picture at **graph.facebook.com/<user id>/picture**. Now I simply set the users profile picture element to that url and it works perfectly.

```javascript
user.fbid   = profile.id;
user.name   = profile.displayName;
user.pic    = 'http://graph.facebook.com/' + profile.id + '/picture';
user.email  = profile.emails[0].value;
```

This solution works well and thanks to Facebook for making their API even simpler!
