---
layout: post
title: Building a Multi-Room Chatroom with Socket.io and Express
---

In this tutorial we will build a multi-room chatroom that also implements unique users leaving and connecting using Socket.io. To achieve this we will keep track of our connected users and their respected websocket on our server. 

First we use **npm** to load our node dependancies **Express.js** and **Socket.io**. Run these commands in your working directory to do so.

```shell
$ npm install socket.io --save
$ npm install express --save
```

Now we will create our Node.js server in a file called **server.js**

```javascript
var port = process.env.PORT || 8080;
var app = require('express')();
var server = require('http').createServer(app);
var io = require('socket.io')(server);

// listen on port 8080
server.listen(port);
console.log("it's wooooorking!");
```

Now run the following command in the terminal

```shell
$ node server.js
```

You now have created a Node.js server listening on port 8080! While this server is nearly useless, well done!

Lets add a default Express route that will send back a simple message for any request. Add the following code to the bottom of **server.js**

```javascript
app.get('*', function(req, res) {
    res.send('well hello there');
});
```

Now point your browser to localhost:8080 were our server is listening. You should be greated with our prepared message.

```javascript
io.sockets.on('connection', function (socket) {

        socketList.push(socket);

        io.emit('new',socketList.length);

        socket.on('joinGroup', function (info) {
            var i = socketList.indexOf(socket);
            socketList[i].roomName = info.roomName;
            socketList[i].userName = info.userName;
            socket.join(info.roomName);

            data[info.roomName].users.push({
                name:info.userName,
                socketIndex: i,
                songTitle:"",
                songURL:null,
                songLink:""
                });

            socket.emit('joined',{});
            socket.broadcast.to(info.roomName).emit('roomChange',info.userName + " joined");
        });
```

Here we create the socket on the server.
