---
layout: post
category : web server
tagline: "Supporting tagline"
tags : [intro,http server]
---

## What is Web (aka) Http Server?

The primary function of a web server is to store, process and deliver web pages to clients. The communication between client and server takes place using the Hypertext Transfer Protocol (HTTP). Pages delivered are most frequently HTML documents, which may include images, style sheets and scripts in addition to text content premodinantely static content.

Although it serve the dynamic content of html pages using php , python , asp plugin to serve the html pages with code embedded in them.

## What are available Http Servers ?

IIS(propietary) , Apache Http Server , nginx , lighthttpd or GWS(propietary) are the popuar webservers in the market. For the sake of this discussion we will pick the key differences between apache and nginx webservers which are open source with more market share.

## Difference between Web Server & Application Server ?

This is one of most widely asked question for anyone not knowing the difference between the two types of servers. For sake of this discussion let me choose Apache Foundations http server(web server)  versus tomcat(appliaction server).

Application server can also hsot web application and render it like web server , so you might as why is web server in place and what does it serve. Application Server is combination of many components atleast in JEE world like web component , ejb component(not available in tomcat) , jmx component etc , it also provides an API for the users to use them to interact with these components in building an application. 

Web Server on the other hand has only core http capabilities to render the html content to the client and communicating between the client and the static pages or the application in the backend. It also bring in features of session replication , load balancing between multiple backend applications based on client load , encapsulating your application server behind & protect it from DDOS attacks or back channel hacking through the port or sql injection etc.

## Apache Vs nginx

The main difference between Apache which is process driven architecture compared to nginx which is event based architecture. So in essence nginx can serve more concurrent users utilizing the computers hardware effectively than apache providing high throughput for static contents. The reason i mentioned static contents is because of the fact that if its dymanic pages like php major bottleneck is in the plugin rather than the webserver itself.

Nginx as mentioned uses a event driven architecture , let me go little bit more to explain what it means by event driven architecture. Nginx ( aka Engine X) operates on a single thread , asynchornous & non bloking architecture. Traditional servers used a thread based model for every request a thread is spawnned which is blocking call & utilizes the CPU, Memory till the request is served with a response hence these are reffered as blocking calls. Apache uses thread based architecture & is dependant on the hardware to scale , unlike nginx which uses single threaded non blocking calls to serve the contents & is scalable to use the hardware effectively to produce better throughput service concurent users effectively.  

Apache recently added multi processing module to its release , but still uses threaded model. But it has been there for a long time with more documentation , support & has more tools avaialble for different configuration needs & lots of plugins are available which are tested and production ready.


## Benefits

Web Servers bring in lots of features and has it place.

1. Load Balancing & failover.
2. URL rewriting.
3. Virtual Hosts.
4. Reverse Proxy or Forward Proxy.

Web Servers can act as a software load balancer between two back end servers using request counting or weighted traffic or pending request or round robin mechanism. It also acts like reverse proxy or forward proxy in between the client and actual application servers serving like an encapsulation in networking terms. It can help us run many servers in the same harward and isolating them virtually as seperate hosts in combination with loadbalaning feature of web servers.

## Conclusion

Web Servers always has its place , the only question is based on the actual requirement its better to choose which webserver serves the purpose. Nginx is the cool kid around the market & has its core web module efficiently architectured to deliver maximum benefit utilizing the underling hardware. Though we must exercise caution as nginx still is early in its maturity model , not strong documentation compared to Apache which has been mature with lots of documentaiton and plugins available it brings with it the bells and whistles of apache foundation as well.
