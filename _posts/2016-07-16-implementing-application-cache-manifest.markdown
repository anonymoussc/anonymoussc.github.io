---
title:  "Implementing application cache manifest"
date:   2016-07-06 19:05:00
summary: which mean once being cache the webapp are accessible offline.

---

HTML5 introduces application cache, which means that a web application is cached, and accessible without an internet connection.

Application cache gives an application three advantages:

1. Offline browsing - users can use the application when they're offline

2. Speed - cached resources load faster

3. Reduced server load - the browser will only download updated/changed resources from the server

Appcache used for this blog :

### manifest.appcache

<script src="http://gist-it.appspot.com/github/anonymoussc/anonymoussc.github.io/blob/2d63af958d5a2e510b8be8f9b92dd99af1468b4c/manifest.appcache?footer=minimal"></script>

### index.html

<script src="http://gist-it.appspot.com/github/anonymoussc/anonymoussc.github.io/blob/2d63af958d5a2e510b8be8f9b92dd99af1468b4c/_layouts/default.html?slice=1&footer=minimal"></script>

---

Notes :

1. It will not cache any videos.

2. It cache all pages except `/contact`.

3. It will cached the latest 14 posts.

