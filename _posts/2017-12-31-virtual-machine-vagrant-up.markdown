---
title:  "Virtual machine : vagrant up"
date:   2017-12-31 12:25:00
categories: Software-Engineering
summary: VM Part 3 vagrant up.
---

This will download the ubuntu/<codename>64 base server (“box”) and run it with our set configuration.

``` bash
vagrant up
```

Once it completed check the status

``` bash
vagrant status
```

Run vagrant ssh to log into the server

``` bash
vagrant ssh
```

### Try command :

- __ll__ - A buit-in alias for the command `ls -alF`, this will list all files within the current directory
- __lsb_release -a__ - A command to show all release information about this server
- __top__ - A command to show running processes and various system information. Use the `ctrl+c` keyboard shortcut to return to the prompt.
- __clear__ - A command to clear currently visible output within your terminal
- __df -h__ - See how much hard drive space is used/ available


---
> Life is one big road with lots of signs. So when you riding through the ruts, don't complicate your mind. Flee from hate, mischief and jealousy. Don't bury your thoughts, put your vision to reality. Wake Up and Live!
> <small>- [Bob Marley](https://www.brainyquote.com/quotes/bob_marley_167100)</small>