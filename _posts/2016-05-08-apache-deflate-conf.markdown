---
title:  "Apache deflate.conf"
date:   2016-05-08 01:07:00
summary: Apache deflate.conf.
---

{% highlight Bash %}
AddOutputFilterByType DEFLATE text/html text/plain text/xml text/event-stream
{% endhighlight %}

{% highlight Bash %}
<Location />
    SetOutputFilter DEFLATE
    SetEnvIfNoCase Request_URI \.(?:gif|jpe?g|png)$ no-gzip dont-vary
    Header append Vary User-Agent env=!dont-vary
</Location>
{% endhighlight %}


Reference :

- [Apache](http://httpd.apache.org/docs/2.4/mod/mod_deflate.html)
- [IIS](http://technet.microsoft.com/en-us/library/cc753681.aspx)
- [nginx,](http://nginx.org/en/docs/http/ngx_http_gzip_module.html)
