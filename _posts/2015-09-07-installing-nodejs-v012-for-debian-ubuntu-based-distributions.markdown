---
title:  "Installing nodejs v0.12 for debian/ubuntu based distributions"
date:   2015-09-07 21:54:00
categories: Software-Engineering NodeJS
---

CLI command :

{% highlight bash %}
# Uninstall previous version
sudo apt-get remove --purge nodejs npm

# New setup script name for Node.js v0.12
curl -sL https://deb.nodesource.com/setup_0.12 | sudo bash -

# Install with:
sudo apt-get install -y nodejs
{% endhighlight %}

[More Information](https://nodesource.com/blog/nodejs-v012-iojs-and-the-nodesource-linux-repositories)


---
> All the best people in life seem to like LINUX. 
> <small>- [Steve Wozniak](http://www.brainyquote.com/quotes/quotes/s/stevewozni349896.html)</small>
