---
title:  "Connecting x/lampp localhost into another pc/laptop"
date:   2016-01-19 03:24:00
summary: Connecting xampp / lampp localhost (accessible) into another personal computer (PC) / laptop.
---

### Set up a virtual host:
Change the `httpd-vhosts.conf`, location of the file :
 - xampp : `C:\xampp\apache\conf\extra\httpd-vhosts.conf`.
 - mampp : `Applications/MAMP/conf/apache/extra/httpd-vhosts.conf`.

Add the following line at the end of the file :

{% highlight bash %}
<VirtualHost *:80>
    DocumentRoot "/Applications/MAMP/htdocs/"
    ServerName someName.whatever
</VirtualHost>
{% endhighlight %}

### Configure your hosts file
Location of the file :
 - MAC : `/private/etc/hosts`.
 - LINUX : `/etc/hosts`.
 - WINDOWS : `\Windows\system32\private\etc\hosts`.
 - WINDOWS 7 : `\Windows\system32\drivers\etc\hosts`.

Add the following line at the end of the file :

{% highlight bash %}
127.0.0.1           someName.whatever
{% endhighlight %}

### Access `someName.whatever` from an other computer

1. Get the IP address of the computer hosting the website
In the terminal, on MAC and LINUX type `ifconfig |grep inet`, on WINDOWS type `ipconfig`

2. Edit the hosts file on the computer you are trying to access the website from.
Refer to the Configure your hosts file section. Add the following line at the end of the file :

{% highlight bash %}
000.000.0.0         someName.whatever
{% endhighlight %}

Change the `000.000.0.0` into ip address value based on the IP address of the computer hosting the website. Using laravel framework type : `sudo php artisan serve --host 0.0.0.0 --port 80`.
Check at [http://someName.whatever](http://someName.whatever).


---
> The library, with its Daedalian labyrinth, mysterious hush, and faintly ominous aroma of knowledge, has been replaced by the computer's cheap glow, pesky chirp, and data spillage.
> <small>- [P. J. O'Rourke](http://www.brainyquote.com/quotes/quotes/p/pjorour617464.html#HZUUYPgyrhXeh21Z.99)</small>
