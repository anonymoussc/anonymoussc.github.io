---
title:  "Virtual machine : file sharing"
date:   2017-12-31 12:30:00
categories: Software-Engineering
summary: VM Part 4 file sharing.
---

A Vagrantfile with the default file sharing configuration in place. This allows us to edit files from our host machine while running the server software within our guest server:

```bash
#File: Vagrantfile
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

config.vm.box = "ubuntu/<codename>64"

config.vm.network :private_network, ip: "192.168.33.10"

# Share Vagrantfile's directory on the host with /vagrant on the guest
config.vm.synced_folder ".", "/vagrant"

end
```

List the contents of the _/vagrant_ directory within server:

```bash
ls -la /vagrant
```

create a new text file in _∼/Sites/sfh_ named hello.txt:

```bash
echo "Hello World" > ~/Sites/sfh/hello.txt
```

```bash
# See files in /vagrant
cd /vagrant
ls -la

# Output the content of "hello.txt"
# with the "cat" command
# Output: "Hello World"
cat /vagrant/hello.txt
```


---
> You don't just wake up one day with dementia or Alzheimer's; these conditions are developmental. Even when a problem triggers the need to collect data, it's reviewed by a specialist and filed away. There's no central repository allowing information to be shared across a multitude of researchers worldwide.
> <small>- [Tan Le](https://www.brainyquote.com/quotes/tan_le_563879)</small>