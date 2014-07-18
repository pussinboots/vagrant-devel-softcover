vagrant-devel-softcover
=============

Setup a ready to use vagrant box for Scala and nodejs with Ubuntu 14.04 base box. The base box only contains the 
Ubuntu 14.04 truly version with all listed development packages see below section Installed software. The vagrant base box is upload to [vagrantcloud.com](https://vagrantcloud.com/).

A tutorial to create a vagrant base box look [here](https://docs.vagrantup.com/v2/boxes/base.html).

##Motivation

Easy to setup Ubuntu based development environment for softcover. Can be used with [vagrant-git](https://github.com/pussinboots/vagrant-git) for an example see [my softcover fork](https://github.com/pussinboots/softcover).

* install vagrant-git with ```npm install -g vagrant-git```
* start vagrant-git with ```vgit --repo pussinboots/softcover``` that will check out my softcover fork and the corresponding vagrant box and start it with vagrant up automaticly
	* on Windows start a command line with Administrator rights [explanation](https://github.com/pussinboots/vagrant-git#requirements) symlink support on shared folders
* in the started virtualbox ```cd /vagrant/project/softcover``` than you are in the softcover project folder
* start development for example with the installed sublime 3 Text Editor

##Requirements

* installed [vagrant](http://www.vagrantup.com/downloads.html) > 1.5
* installed [vagrant-vbguest](https://github.com/dotless-de/vagrant-vbguest) ```vagrant plugin install vagrant-vbguest```
* installed [virtualbox](https://www.virtualbox.org/wiki/Downloads)

##Vagrant

* setup with the ssh key used by vagrant 
* no chef or puppet installed
# no provisioner used

###User

* username: vagrant
* password: vagrant
* has sudo rights

###Operating System

Ubuntu 14.04 with gnome-session-flashback (2d) window manager because the default unity needs 3d support and that slow down the vm by using software rendering for it.

###Installed software

* java 8 oracle jdk
* git 
* conscript
* sublime 3 text editor
* sbt 0.13.5
* heroku
* nvm
* nodejs 0.10.28
* travis
* gnome-session-flashback
* softcover-nonstop version my fork see [here](https://github.com/pussinboots/softcover)
* texlive latex distribution 
* inkscape
* calibre
* epubcheck
* kindlegen

All installed software can be used as user vagrant from the command line. Idea is intalled as menu item under Programming entry.

##Usage

1. clone this repo with ```git clone git@github.com:pussinboots/vagrant-devel-softcover.git```
2. ```cd vagrant-devel-softcover```
3. look into the Vagrantfile and adapt if it nessary like reduce or increase memory
4. start up vagrant with ```vagrant up``` can take a while has to be download 1.2 GB base box (only first time)

##Vagrantfile

This configure vagrant to use the  [vagrantcloud](https://vagrantcloud.com/pussinboots/ubuntu-truly-softcover) hosted base base. 
```ruby
config.vm.box = "pussinboots/ubuntu-truly-softcover"
```