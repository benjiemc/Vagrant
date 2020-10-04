# Vagrant

Settings for setting up vagrant VMs for development in a linux environment.

To begin, install the latest versions of [VirtualBox][1] and [Vagrant][2]

## Basic Box Setup

To begin, clone this git repository using ssh or https.

Using ssh:
```shell
git clone git@github.com:benjiemc/Vagrant.git ~/vagrant
```

or using https:
```shell
git clone https://github.com/benjiemc/Vagrant.git ~/vagrant
```

Next change into the vagrant directory:
```shell
cd ~/vagrant/
```

And start the vagrant box:
```shell
vagrant up
```

When the box has finally loaded, enter it by using the command
```shell
vagrant ssh
```
By default, this has setup the `python` box used for python development.


## `python` box Setup

Follow the same first two steps- cloning the git repository and changing into the vagrant directory.

Then run the commands:
```shell
vagrant up python
```
Followed by... 
```shell
vagrant up python
```
And voilà, you should be in the `ubuntu 20.04` box ready for python 3
development. 

[1]: https://www.virtualbox.org/wiki/Downloads
[2]: https://www.vagrantup.com/downloads.html
