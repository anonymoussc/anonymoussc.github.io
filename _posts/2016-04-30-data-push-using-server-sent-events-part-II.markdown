---
title:  "Data Push using Server Sent Events - part II"
date:   2016-04-30 21:22:00
categories: SSE
summary: Server-sent events (SSE) is a technology where a browser receives automatic updates from a server via HTTP connection - Wikipedia.
---

- `Object.keys` is available in all browsers where SSE is also available. When we start adding fallbacks we will need a polyfill for IE8 and earlier. The polyfill is slower: it is an `O(n)` algorithm (where n is the number of keys), whereas a native `Object.keys` should be `O(1)`.

- With persistent storage we can store all the data that is streamed to us, opening up a world of possibilities: tables, real-time charts, client-side analysis using the latest machine learning technologies, and so on.



Reference :

1. [Server-sent events Web APIs MDN](https://developer.mozilla.org/en-US/docs/Web/API/Server-sent_events)

2. Data Push Apps With HTML5 SSE: Pragmatic Solutions for Real-World Clients, Darren Cook, O'Reilly Media, Mar 2014. isbn:9781430264484, isbn:9781449371937, amazon:1449371930, google:7gYiAwAAQBAJ

3. [Wikipedia](https://en.wikipedia.org/wiki/Server-sent_events)


---
> Imagination will often carry us to worlds that never were. But without it we go nowhere.
> <small>- [Carl Sagan](http://www.brainyquote.com/quotes/quotes/c/carlsagan131315.html)</small>