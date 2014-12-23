---
layout: post
title: Building a Multi-Room Chatroom with Socket.io and Node
---

In this tutorial we will build a multi-room chatroom that also implements unique users leaving and connecting using Socket.io. To achieve this we will keep track of our connected users and their respected websocket on our server.
          
{% highlight javascript %}
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
                });
            socket.emit('joined',{});
            socket.broadcast.to(info.roomName).emit('roomChange',info.userName + " Joined the Party!");
        });

        socket.on('message', function(data) {
            console.log(data);
            io.sockets.in(data.roomName).emit("message", data.message);
        })

        socket.on('enter', function() {
           io.emit('totalChange',{});
        });

        socket.on('disconnect', function() {
            var i = socketList.indexOf(socket);

            var rmNm = socketList[i].roomName;
            if(rmNm) {
                var usNm = socketList[i].userName;

                var k = -1;
                for (var i = 0; i < data[rmNm].users.length; ++i) {
                    if (data[rmNm].users[i].name == usNm) k = i;
                }

                //Remove User Info
                if (data[rmNm].users.length > 1) {
                    data[rmNm].users.splice(k, 1);
                    io.sockets.in(rmNm).emit('left', {userName: usNm});
                    io.emit('totalChange',{});
                }
                else {
                    delete data[rmNm];
                    io.emit('totalChange',{});
                }
            }
        });
    });
{% endhighlight %}

Here we create the socket on the server.
