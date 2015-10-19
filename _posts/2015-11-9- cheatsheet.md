---
layout: post
category : productivity
tagline : reference
tags : [git,vagrant,docker]
---

##### Table of Contents  
[vagrant](#vagrant)  
[git](#git)  
[docker](#docker)  


<a name="vagrant"/>

## vagrant

action|command|
:---:|:---:|
create vagrant file|vagrant init **boxname**|
bringing vm up|vagrant up|
reloading vagrant config|vagrant reload|
shutting down the vm|vagrant halt|
destroy the vm|vagrant destory|

<a name="git"/>

## git

action|command|
:----:|:----:|
to clone the git repository|git clone url|
commits new files to your repository|git add *|
commits git repository changes|git commit -m "message"|
pushing changes to git repository|git push origin **master**|
refreshing git repository|git pull origin **master**|
overwrite git repository|git reset ---hard **master** , git pull (or) git stash , git pull|
clean repository of untracked files & folders|git clean -dfx|
creating a new branch| git branch **branchname**|
switching branch| git checkout *branchname*|
deleting branch| git branch -rd origin/**branchname**|
refreshing deleted file| git checkout **filename**|


<a name="docker"/>

## docker

action|command|
:----:|:----:|
removing docker image|docker rmi **imagename**|
list docker images|docker images|
creating docker image|docker build **imagename** |
removing a container|docker rm **containername** |
starting a container|docker start **containername** |
stoping a container|docker stop **containername** |
restarting a container|docker restart **containername** |
starting a container with port exposed and data volume mounted|docker run -d --name *containername* -p *hostport*:*contport* **imagename**|
renaming an existing image|docker tag **imagename**:**latest** **newname**|
listing current running containers|docker ps|
listing all containers running & exited | docker ps -a|
removing all containers which exited | docker rm $(docker ps -a -q)|
removing all images | docker rmi $(docker images -q)|
