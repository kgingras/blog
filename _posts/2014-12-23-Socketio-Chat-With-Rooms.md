---
layout: post
title: Building a Multi-Room Chatroom with Socket.io and Node
---

In this tutorial we will build a multi-room chatroom that also implements unique users leaving and connecting using Socket.io. To achieve this we will keep track of our connected users and their respected websocket on our server.
          
{% highlight javascript %}
var event = function() {
          console.log("hey");
}
{% endhighlight %}

Here we create the socket on the server.
