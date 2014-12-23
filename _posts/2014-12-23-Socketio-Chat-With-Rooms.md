---
layout: post
title: Building a Multi-Room Chatroom with Socket.io and Node
---

In this tutorial we will build a multi-room chatroom that also implements unique users leaving and connecting using Socket.io. To achieve this we will keep track of our connected users and their respected websocket on our server.
          
          ``` javascript
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

            socket.broadcast.to(info.roomName).emit('roomChange',info.userName + " Joined the Party!");

        });
```

Here we create the socket on the server.
