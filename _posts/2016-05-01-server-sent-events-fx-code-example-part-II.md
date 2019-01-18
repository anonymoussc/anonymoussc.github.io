---
title:  "Server Sent Events fx code example - part ll"
date:   2016-05-01 21:18:00
categories: SSE
summary: Server-sent events (SSE) Foreign Exchange (fx) client - server code example part II.
---

### 1. SSE fx client - server structured code example.

{: .center-text}
fxpair1.structured.php

<script src="https://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse4/fxpair1.structured.php?footer=minimal"></script>

{: .center-text}
fxserver1.structured.php

<script src="https://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse4/fxserver1.structured.php?footer=minimal"></script>

{: .center-text}
fxclient1.basic.structured.html

<script src="https://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse4/fxclient1.basic.structured.html?footer=minimal"></script>

### 2. SSE fx client - server with history code example.

{: .center-text}
fxserver2.structured.php

<script src="https://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse4/fxserver2.structured.php?footer=minimal"></script>

{: .center-text}
fxclient2.history.html

<script src="https://gist-it.appspot.com/github/apps-libX/appsse937/blob/dev-master/sse4/fxclient2.history.html?footer=minimal"></script>

### SSE Notes

- `Object.keys` is available in all browsers where SSE is also available. When we start adding fallbacks we will need a polyfill for IE8 and earlier. The polyfill is slower: it is an `O(n)` algorithm (where n is the number of keys), whereas a native `Object.keys` should be `O(1)`.

- With persistent storage we can store all the data that is streamed to us, opening up a world of possibilities: tables, real-time charts, client-side analysis using the latest machine learning technologies, and so on.


Reference :

1. [Server-sent events Web APIs MDN](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events)

2. Data Push Apps With HTML5 SSE: Pragmatic Solutions for Real-World Clients, Darren Cook, O'Reilly Media, Mar 2014. isbn:9781430264484, isbn:9781449371937, amazon:1449371930, google:7gYiAwAAQBAJ

3. [Wikipedia](https://en.wikipedia.org/wiki/Server-sent_events)


---
> We're entering a new world in which data may be more important than software.
> <small>- [Tim O'Reilly](https://www.brainyquote.com/quotes/quotes/t/timoreill219565.html)</small>