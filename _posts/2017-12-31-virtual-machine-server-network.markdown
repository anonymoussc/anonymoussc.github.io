---
title:  "Virtual machine : server network"
date:   2017-12-31 12:35:00
categories: Software-Engineering
summary: VM Part 5 server network.
---

check out the network configuration.

```bash
ifconfig
```

The result, each network is called an _“interface”_.

- __lo__ - The loopback interface. This is used for internal communication between services within the server. This is _“localhost”_ - `127.0.0.1`.
- __eth0__ and __eth1__ - These are two additional networks created as well. We can see the IP address we assigend the server at __eth1__ - `192.168.22.10`. The server also has its own private network, with the IP address `10.0.2.15` assigned to this machine.


---
> First, our focus on security is on the infrastructure itself. So it is all about how you protect the network, the device, and the application that is riding on the server.
> <small>- [John W. Thompson](https://www.brainyquote.com/quotes/john_w_thompson_339843)</small>