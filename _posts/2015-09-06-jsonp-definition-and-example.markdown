---
title:  "Jsonp definition and example"
date:   2015-09-06 00:03:03
categories: Software-Engineering JSONP
summary: JSONP definition (wikipedia) and implementation example. 
---

> JSONP or "JSON with padding" is a communication technique used in JavaScript programs running in web browsers to request data from a server in a different domain, something prohibited by typical web browsers because of the same-origin policy. 
> <small>- [JSONP - Wikipedia, the free encyclopedia](https://en.wikipedia.org/wiki/JSONP)</small>

Example (simple jQuery-driven AJAX call) :

{% highlight JavaScript %}
/**
 * Created by anonymoussc on 9/6/15 11:20 PM.
 */

$.ajax({
    url         : "https://path/to/resource/",
    dataType    : 'jsonp',
    crossDomain : true,
    success     : function (data) {
        $('#list').html(data.count + 'True');
    },
    error       : function (data) {
        $('#list').html('False');
    }
});
{% endhighlight %} 


---
> The kind of programming that C provides will probably remain similar absolutely or slowly decline in usage, but relatively, JavaScript or its variants, or XML, will continue to become more central. 
> <small>- [Dennis Ritchie](https://www.brainyquote.com/quotes/quotes/d/dennisritc274077.html)</small>
