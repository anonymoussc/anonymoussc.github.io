---
title:  "Data Push Using Server Sent Events"
date:   2016-04-15 21:44:00
summary: Server-sent events (SSE) is a technology where a browser receives automatic updates from a server via HTTP connection - Wikipedia.
---

Server-sent events (SSE) is a technology where a browser receives automatic updates from a server via HTTP connection - [Wikipedia](https://en.wikipedia.org/wiki/Server-sent_events).

- Server-Sent Events (SSE) is an HTML5 technology that allows the server to push fresh data to clients (commonly called data push).
- Data push is where the server chooses to send new data to the clients.
- SSE excels when you need to update part of a web application with fresh data, without requiring any action on the part of the user.
- Anything you can do with WebSockets can be done with SSE, and vice versa, but each is better suited to certain tasks.

### First example : basic SSE

- first.html

<script src="http://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse2/first.html?footer=minimal"></script>

- first.php

<script src="http://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse2/first.php?footer=minimal"></script>


Reference :

1. [Wikipedia](https://en.wikipedia.org/wiki/Server-sent_events)

2. Data Push Apps With HTML5 SSE: Pragmatic Solutions for Real-World Clients, Darren Cook, O'Reilly Media, Mar 2014. isbn:9781430264484, isbn:9781449371937, amazon:1449371930, google:7gYiAwAAQBAJ
