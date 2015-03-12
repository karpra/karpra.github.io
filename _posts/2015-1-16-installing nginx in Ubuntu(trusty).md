---
layout: post
category : server
tags : [nginx]
---

# Installing nginx in Ubuntu 14.04 #

## Introduction ##

Nginx is one of the most popular web servers in the world and is responsible for hosting some of the largest and highest-traffic sites on the internet. It is more resource-friendly than Apache in most cases and can be used as a web server or a reverse proxy.

I am going to create a Virtual Machine which will run Linux OS in our case Ubuntu Linux 64 bit ( Trusty for version 14.04 ) for sake of mimicking as much close to production environment. I have used __Vagrant__ for managing my virtual machine and provisioning it for I can be saved from hastle of downloading a Ubuntu Linux ISO and installing on newly created Virtual Machine. 

## Pre-Requisite ##
1. __Vagrant__
2. __VirtualBox__

If you are not familiar with Vagrant ,Please refer to my article on Vagrant & its use [here](http://karpra.github.io/devops/2014/09/19/introduction%20to%20vagrant/)

Although I am provisioning a Ubuntu box , you are free to choose your preference of OS from the list of available
[Vagrant boxes](http://www.vagrantbox.es/)

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

You can ssh into the Virtual Machine by using the below command.
		
	vagrant ssh

You can run command to check the ipaddress of the machine using
		
	ifconfig

Vagrant assigns a ip address by default from your router or DHCP Server , which is dynamic.
But for the sake of experimentation we do not need to go through the details of DHCP Configuration , although
we can define out own private network for you to access it on the machine you have created your virtual machine.
    
You can edit your Vagrantfile & uncomment the below line and assign a ip address like 192.168.33.10

    config.vm.network "private_network", ip: "192.168.33.10"
 
 Once you do that you should load the recent changed by using the below command
 
	 vagrant reload (or) vagrant halt followed by vagrant start

You can continue to use vagrant ssh or ssh manually using below command in terminal or putty( in windows).
    
	ssh vagrant@192.168.33.10 (or) vagrant ssh
    
##  Install ##

I have provisioned a ubuntu box using vagrant and i will go over details of installation of nginx in the provisioned ubuntu linux.

    vagrant@vagrant-ubuntu-trusty-64:~$ sudo apt-get upgrade
    vagrant@vagrant-ubuntu-trusty-64:~$ sudo apt-get update
    vagrant@vagrant-ubuntu-trusty-64:~$ sudo apt-get install nginx
    
You should see the nginx server running in the box & you can check if its running by using following command below.

    vagrant@vagrant-ubuntu-trusty-64:~$ ps -ef | grep nginx
    root      1093     1  0 Jan15 ?        00:00:00 nginx: master process /usr/sbin/nginx
    www-data  1094  1093  0 Jan15 ?        00:00:24 nginx: worker process
    www-data  1095  1093  0 Jan15 ?        00:00:00 nginx: worker process
    www-data  1096  1093  0 Jan15 ?        00:00:26 nginx: worker process
    www-data  1097  1093  0 Jan15 ?        00:00:26 nginx: worker process
    vagrant   9206  9185  0 21:31 pts/0    00:00:00 grep --color=auto nginx

So now should you go to the browser and type this http://192.168.33.10/

You should be able to see nginx serving and displaying something on the browser.
