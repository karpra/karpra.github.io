---
layout: post
category : devops
tagline: "Supporting tagline"
tags : [automation]
---

## What is Vagrant?

Vagrant is an amazing dev productivity tool for managing virtual machines using command line which lets run the virtual machine in headless mode. It is template based and can be extended to a standard box and its fast enough to boot the virtual machine using this tool.


Please download vagrant [here](https://www.vagrantup.com/) 

## Motivation

The main reasoning to use virtual machine during development is to isolate environments in a seperate container than messing up with different versions of jdk or python etc any sdks or multiple application servers creating conflicts etc & having to support different versions in host machine. I have been a big proponent of developing applications mimicing as much as running in typical isolated environments hosted in linux enviroments just as much finally the shipped product will ultimately run on it.

Ofcourse we can maintain isolation in case of python environments using [virtualenv](http://virtualenv.readthedocs.org/en/latest/)
& run different version of jdk in case of java but have to constantly update the java home variable in mac or create a bash or cmd script to set the java home based on the version being used. I liked the idea of not having to manage version dependencies and freeze an environment to do development and not to worry about managing different version of software etc to be installed in host machine & also should i migrate the virtual machine to another machine its straight forward and i can avoid going through process of installation of softwares etc & i can replicate the virtual machine using export options.

Since i am a big proponent of open source I started using [Virtual Box](https://www.virtualbox.org/) , it solved environment isolation problem & dependency issues aiding in keeping the host machine cleaner with no trace of software version installed for runtime , ofcourse it not entirely true as u need jdks or python versions installed for ide to use and compile code to be deployed for runtime container in vm.

You can ofcourse use VMWare solution to provision a VM , i thought it was bulky for development environments. Sometimes u will need VMWare licensed software to run on mac which is what i use.

## Why Vagrant?

Before vagrant existed i use to provision a vm for a given OS lets say Linux 64 bit Ubuntu version , I will go about downloading the iso image & installed in a virtual machine and then go about installing other softwares to keep the environment ready for code to be deployed for testing purpose. This ensured i had a linux environment hosting application just as much a smaller subset of production kind of environment ofcourse without benefits of clustering as i thought it was overkill to do development in a clustered environment unless the software or application has cluster aware features. 

This whole process was time consuming & managing was difficult , but once created it had the same benefits of isolated linux enviornment running app servers or servers. I would probably keep a golden copy of virtual machine hard disk installed with os & export and keep it ready to import for next use into another virutal machine though it had its own issues of lot of time in importing and exporting virtual machine hard disk as OVF file.


Vagrant helped in process of providing a readily available box which can be added to vagrant environment which still uses virtual box but its much faster and quicker to add than import export. Also it helped not just provide base boxes for different OS but also help in running the virtual machines seemlessly in a headless fashion.


## Using Vagrant

Vagrant provides set of already created boxes referred as base boxes.Please feel free to download the vagrant base box [here](http://www.vagrantbox.es/)

You can download these bases boxes or few vagrant boxes are also provisioned in github projects.

I will create a vagant box and host in my github to try downloading at some point for reference.

Once the base box is downloaded , we go about initializing the vagant file to use the box.

    vagrant init baseboxurl

This should create a Vagrant File for you to edit and use to your needs.

Customizing the vagrant file for usage 

    config.vm.box = "<http://baseboxurl>" 
    config.vm.network "private_network", ip: "192.168.66.66"
    config.vm.synced_folder "data", "/data/"
    
This is made part of private network to access the virtual machine using the given ip address & then we create a sync folder between host and virtual machine. So we can transfer any code , downloadables or code artifacts in shared location using host ide and be able to build and deploy easily in virtual machine if administration console is not an option.
    

Further you can add the base box and use it as reference to create another vagrant based virtual machine , the idea of base box is to be used like standard template.

    vagrant add box ubuntubasebox
    

Once the box is avaiable in vagrant we can modify the Vagrant file to start using it directly from vagrant repository than looking up the reference from basebox url.

    config.vm.box = "<box name>"

Starting the virtual machine using vagrant

    vagrant up
    
Stopping the virtual machine using vagrant

    vagrant halt
    
Once the virtual machine is up and running you can ssh into the ipaddress mentioned above and login to the linux machine.

    username/password - vagrant/vagrant
                      - root/vagrant
                      
Once the container is ready you are free to install the software required and you can export a environment with database , app server , http servers etc and export them into a template & distribute for easy usage.
