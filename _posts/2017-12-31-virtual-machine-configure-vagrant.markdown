---
title:  "Virtual machine : configure vagrant"
date:   2017-12-31 12:15:00
categories: Software-Engineering
summary: VM Part 1 configure vagrant.
---

### On Mac:

``` bash
mkdir -p ~/Sites/sfh
cd ~/Sites/sfh
vagrant init ubuntu/<codename>64
```

### On Windows:

``` bash
mkdir C:\sfh
cd C:\sfh
vagrant init ubuntu/<codename>64
```

### File: Vagrantfile

``` bash
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

config.vm.box = "ubuntu/<codename>64"

end
```


---
> The mind of a child is no less vagrant than his steps; it pursues the gossamer and flies from object to object, lawless and unconfined, and it is equally necessary to the development of his frame that his thoughts and his body should be free from fetters.
> <small>- [William Godwin](https://www.brainyquote.com/quotes/william_godwin_778398)</small>