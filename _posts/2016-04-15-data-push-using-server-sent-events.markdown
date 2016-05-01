---
title:  "Data Push using Server Sent Events"
date:   2016-04-15 15:57:00
categories: SSE
summary: Server-sent events (SSE) is a technology where a browser receives automatic updates from a server via HTTP connection - Wikipedia.
---

Server-sent events (SSE) is a technology where a browser receives automatic updates from a server via HTTP connection - [Wikipedia](https://en.wikipedia.org/wiki/Server-sent_events).

- Server-Sent Events (SSE) is an HTML5 technology that allows the server to push fresh data to clients (commonly called data push).
- Data push is where the server chooses to send new data to the clients.
- SSE excels when you need to update part of a web application with fresh data, without requiring any action on the part of the user.
- Anything you can do with WebSockets can be done with SSE, and vice versa, but each is better suited to certain tasks.
- The `EventSource` JavaScript object is used to receive server-sent event notifications.
- Each time an update is received, the `onmessage` event occurs.
- In Apache, each SSE connection is not just using a socket, but it is also using up a thread or process in Apache. 
- In PHP, it's starting a new PHP instance specific for the connection. 
- Apache and PHP will be using a chunk of memory, that limits the number of simultaneous connections can be supported.
- `Event handler` also referred to as a `callback`. In JavaScript, objects generate events, and each object has its own set of events we might want to listen for.
  

### Question and Answer

1. How often are server-side events going to happen?
- The higher this is the better data push (whether SSE or WebSockets) will be.

2. How often are client-side events going to happen?
- If such events occur less than once every five seconds, and especially if there is less than one event every second, WebSockets is going to be a better choice than SSE. If such events occur less than once every 5 to 10 seconds, this becomes a minor factor in the decision-making process.

3. Are the server-side events not just fairly infrequent but also happening at predictable times?
- When such events are less frequent than once a minute, data pull has the advantage that it won’t be holding open a socket. Be aware of the issues with lots of clients trying to all connect at the same time.


Reference :

1. [Server-sent events - Web APIs | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events)

2. Data Push Apps With HTML5 SSE: Pragmatic Solutions for Real-World Clients, Darren Cook, O'Reilly Media, Mar 2014. isbn:9781430264484, isbn:9781449371937, amazon:1449371930, google:7gYiAwAAQBAJ

3. [Wikipedia](https://en.wikipedia.org/wiki/Server-sent_events)


---
> Ideas shape the course of history.
> <small>- [John Maynard Keynes](http://www.brainyquote.com/quotes/quotes/j/johnmaynar129999.html)</small>