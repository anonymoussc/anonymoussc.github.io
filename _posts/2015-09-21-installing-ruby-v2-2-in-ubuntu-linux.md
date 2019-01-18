---
title:  "Installing Ruby v2.2 in Ubuntu Linux"
date:   2015-09-21 12:38:00
categories: Linux Ubuntu
summary: Step by step installing ruby v2.2 in the latest ubuntu linux (15.04).
---

CLI command :

{% highlight bash %}
# Uninstall previous version
sudo apt-get remove --purge ruby ruby-dev

# Install with :
sudo apt-add-repository ppa:brightbox/ruby-ng
sudo apt-get update
sudo apt-get install ruby2.2

# Optional :
# ERROR: Failed to build gem native extension.
sudo apt-get install ruby2.2-dev
sudo apt-get install build-essential

# Nokogiri failed to install error
sudo apt-get install ruby-dev zlib1g-dev

# Nokogiri error libxml2 is missing
sudo apt-get install libxslt-dev libxml2-dev

# OpenSSL certificate verify failed
# Error : Gem::RemoteFetcher::FetchError: SSL_connect SYSCALL returned=5 errno=0 state=SSLv3 read server session ticket A (https://rubygems.org/gems/html-pipeline-1.9.0.gem)
# In Gemfile change source 'https://rubygems.org' into source 'http://rubygems.org'
{% endhighlight %}


---
> Ruby inherited the Perl philosophy of having more than one way to do the same thing. I inherited that philosophy from Larry Wall, who is my hero actually. I want to make Ruby users free. I want to give them the freedom to choose. 
> <small>- [Yukihiro Matsumoto](https://www.brainyquote.com/quotes/quotes/y/yukihiroma213504.html)</small>
