---
title:  "Swappines parameter (Ubuntu 15.10)"
date:   2016-02-29 01:58:00
summary: The swappiness parameter controls the tendency of the kernel to move processes out of physical memory and onto the swap disk.
cover-image: minion-lenses-attitude-uniform_1024.jpg
---

The swappiness parameter controls the tendency of the kernel to move processes out of physical memory and onto the swap disk. Because disks are much slower than RAM, this can lead to slower response times for system and applications if processes are too aggressively moved out of memory.

### Check the swappiness value

To check the swappiness value, in the terminal type : 

    cat /proc/sys/vm/swappiness

### Temporary change the swappiness value

To temporally (will lost on reboot) change the swappiness value, in the terminal type : 

    sudo sysctl vm.swappiness=10

### To make a permanent change, edit the configuration file.

{% highlight Bash %}
# Using kate text editor
gksudo kate /etc/sysctl.conf

# Using gedit text editor
gksudo gedit /etc/sysctl.conf
{% endhighlight %}

Add or edit to the end of the file the swappiness value of choice, default setting for ubuntu are 60.

    vm.swappiness=10 

Save and reboot.


---
> I wouldn't swap the era I competed in for anything, not a day of it. I started out as an amateur, and people like myself, Seb Coe, Steve Ovett, Steve Cram, Tessa Sanderson and the rest did it for the glory of winning medals for our country.
> <small>- [Daley Thompson](https://www.brainyquote.com/quotes/quotes/d/daleythomp521652.html)</small>