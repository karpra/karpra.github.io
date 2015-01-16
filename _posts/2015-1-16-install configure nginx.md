---
layout: post
category : server
tagline: "Supporting tagline"
tags : [install,http server]
---

Introduction

Nginx is one of the most popular web servers in the world and is responsible for hosting some of the largest and highest-traffic sites on the internet. It is more resource-friendly than Apache in most cases and can be used as a web server or a reverse proxy.


Pre-requisties
  Vagrant
  VirtualBox

Please refer to my article on Vagrant & its use [here](http://karpra.github.io/devops/2014/09/19/introduction%20to%20vagrant/)

    vagrant init ubuntu/trusty64
    vagrant up
    
Once this command is initiated the machine will start booting up and you should see something similar to the below command.

    Bringing machine 'default' up with 'virtualbox' provider...
    ==> default: Checking if box 'ubuntu/trusty64' is up to date...
    ==> default: Resuming suspended VM...
    ==> default: Booting VM...
    ==> default: Waiting for machine to boot. This may take a few minutes...
        default: SSH address: 127.0.0.1:2222
        default: SSH username: vagrant
        default: SSH auth method: private key
        default: Warning: Connection refused. Retrying...
    ==> default: Machine booted and ready!
    
Now you can ssh into the machine based on the configuration of the Vagrant File if you want to do it manually.

    config.vm.network "private_network", ip: "192.168.33.10"

    > ssh vagrant@192.168.33.10 (or) vagrant ssh
    
Install

I have provisioned a ubuntu box using vagrant and i will go over details of installation of nginx in the provisioned ubuntu linux.

    vagrant@vagrant-ubuntu-trusty-64:~$ sudo apt-get upgrade
    vagrant@vagrant-ubuntu-trusty-64:~$ sudo apt-get update
    vagrant@vagrant-ubuntu-trusty-64:~$ sudo apt-get install nginx






