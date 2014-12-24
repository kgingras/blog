---
layout: post
title: Building a Multi-Room Chatroom with Socket.io and Node
---

In this tutorial we will build a multi-room chatroom that also implements unique users leaving and connecting using Socket.io. To achieve this we will keep track of our connected users and their respected websocket on our server.

Test Test
Test test
          
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

            socket.broadcast.to(info.roomName).emit('roomChange',info.userName + " Joined the Party!");

        });

        socket.on('lock',function(song) {
            var i = socketList.indexOf(socket);
            var k =  data[socketList[i].roomName].users.map(function(x) {return x.name; }).indexOf(socketList[i].userName);
            data[socketList[i].roomName].users[k].songTitle = song.title;

            io.sockets.in(socketList[i].roomName).emit('change',{});
        });


        // MESSAGE EVENTS

        socket.on('message', function(data) {
            console.log(data);
            io.sockets.in(data.roomName).emit("message", data.message);
        })

        // USER ACTIONS EVENTS

        socket.on('searching',function(data) {

        });

        socket.on('enter', function() {
           io.emit('totalChange',{});
        });

        socket.on('end', function() {

        })

        socket.on('loaded', function(id) {

        })

        socket.on('start', function(data) {
            var then = new Date().getMilliseconds();
            io.sockets.in(data).emit('play',then);
        })

        socket.on('LoadAll', function(data) {
            io.sockets.in(data).emit('load',data);
        })

        // Bring back pplayers current timer;
        socket.on('timeCheck', function(data) {
            // IMPLEMENT
        });

        //  To reload everyones data
        socket.on('loading', function (data){
            io.sockets.in(data).emit('reload',{});
        })

        socket.on('end', function (data) {

            // Get Everybody and then push play;

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
            socketList.splice(i, 1);
            io.emit('new',socketList.length);
        });
    });
```

Here we create the socket on the server.
