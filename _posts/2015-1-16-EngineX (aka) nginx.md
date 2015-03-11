---
layout: post
category : server
tagline: "Supporting tagline"
tags : [nginx]
---

<h1>Introduction</h1>

Nginx is one of the most popular web servers in the world and is responsible for hosting some of the largest and highest-traffic sites on the internet. It is more resource-friendly than Apache in most cases and can be used as a web server or a reverse proxy.


<h2>Pre-Requisite</h2>
1. Vagrant
2. VirtualBox

Please refer to my article on Vagrant & its use [here](http://karpra.github.io/devops/2014/09/19/introduction%20to%20vagrant/)

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
    
Now you can ssh into the machine based on the configuration of the Vagrant File 

    config.vm.network "private_network", ip: "192.168.33.10"

You can choose to ssh manually or use vagrant to ssh as mentioned below.
    
<pre><code>ssh vagrant@192.168.33.10 (or) vagrant ssh</code></pre>
    
<h2>Install</h2>

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

You should be able to see nginx running.








