
system design is actually matter is when your application is growing and you need to scale it. It is a process of defining the architecture, components, modules, interfaces, and data for a system to satisfy specified requirements.


.
your app server =======> database

one server is holding you app and one database is holding your data. If your app is growing and you need to scale it, you can add more servers to handle the load. This is where system design comes into play. itse enough for thousands of users.


# LOAD BALANCER
suppose you build an ticket booking application. You have a single server that is handling all the requests from users. suppose there is an trending movie and thousands of users are trying to book tickets at the same time. Your single server will not be able to handle all the requests and will crash. To handle this load, you can add more servers and use a load balancer to distribute the requests among the servers. This way, your application can handle thousands of users without crashing.

when thousand of request come at a time, yourthey pile up in a queue and wait for the server to process them. This will increase the response time and users will have a bad experience.

two options to handle this load:
1. vertical scaling: adding more resources (CPU, RAM) to your existing server. This is limited by the maximum capacity of the server and can be expensive. it will become costlier as you need to keep upgrading your server to handle more load.
2. horizontal scaling: adding more servers to handle the load. This is more cost-effective and allows for better fault tolerance. If one server goes down, the load balancer can redirect traffic to the other servers. more machines sharing the loads.

- server 1 , server 2 , server 3. these  are not threee different part of your application. this is not one server for payment one server for messaging one server for booking. these are three different servers handling the same application. all three servers are running the same code and can handle any request from any user. this is called horizontal scaling. three identical copies of your app running at the same time. the same code running three times. each copy can handle any request from any user. if one server goes down, the load balancer will redirect the traffic to the other two servers. this way, your application can handle thousands of users without crashing.
- this doesnt mean you deploy your application on three times. you ship it one once. you just tell your platform to run three instances of it.

- when a request comes from an user  which server it goest to. something stand in front of the server and hand each incoming request to one of them, spread the people out evenly so no single server get overwhelmed while the others sit idle. and that thing is called load balancer

- nginx is a classic one and if you deploy of something like vercel or railway you already have an load balance you dont have to think about it.if the load balancer goes down it doesnt matter that you have three healthy servers behing it, nobody can reach them so in real systems the load balancer itselft also has a backup which is more stuff to run.and there is also a second cost which is quieter and its breaks something that you cant even see. for the load balancer to send any request to any server, all your servers have to be interchangable. Any of them hast to be able to handle any request and right now they are not.


# STATELESS SERVERS

- so now we are running multiple instances of our app . that creates problem that you didnt have with just one.
- if you logged in on server 1 and u get the session token but only it keeps in the memory of server 1 and server 2 and other server dont know about u. so they asked to logged in again.
- to fix the servers are not allowed to remeber anything about you between requests. no server keeps a note in its own memory . instead node goes somewhere all of them can reach a seperate place off to the side that every server can read from and write to.
-  when you logged in the note will get to the shared place and then on the next click  there server reads the same shared place finds your notes  and know its you
- Redis for example.


# CONNECTION POOLING AND READ REPLICAS
- what if the app slow again. we done load balance and different still slow mean need to notice that the servers have in common one database. we scale the serves but we didnt scale the thing behind them database.
- 1 problem. the db is talk to somany people at once . 