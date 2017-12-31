---
title:  "Virtual machine : networking"
date:   2017-12-30 12:20:00
categories: Software-Engineering
summary: VM Part 2 networking.
---

### File: Vagrantfile

``` bash
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

config.vm.box = "ubuntu/<codename>64"

config.vm.network :private_network, ip: "192.168.33.10"

end
```

Notes :
- The _private_network_ directive tells __Vagrant__ to setup a private network. PC host and guest machines can communicate on this network. This assigns the guest server the IP address of `192.168.33.10`. Note that each server should have a unique IP address just in case they are run at the same time.

- There are IP address ranges set aside for private networks. Generally we can use `10.0.0.0` - `10.255.255.255`, `172.16.0.0` - `172.31.255.255`, and `192.168.0.0` - `192.168.255.255`. However, always avoid the lower and upper IP addresses within those ranges, as they are often reserved.


---
> My Golden Rule of Networking is simple: Don't keep score.
> <small>- [Harvey Mackay](https://www.brainyquote.com/quotes/harvey_mackay_528742)</small>