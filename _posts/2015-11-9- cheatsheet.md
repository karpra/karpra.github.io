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
[k8s](#k8s)  


<div id="vagrant"/>
#### vagrant

action|command|
:---:|:---:|
create vagrant file|vagrant init **boxname**|
bringing vm up|vagrant up|
reloading vagrant config|vagrant reload|
shutting down the vm|vagrant halt|
destroy the vm|vagrant destory|

<div id="git"/>
#### git

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
deleting branch| git branch -rd origin/**branchname** (or) git push origin --delete **branchname**|
refreshing deleted file| git checkout **filename**|
creating a branch of an existing branch| git checkout -b **newbranchname** **oldbranchname**|
merging two branches| git checkout **branchnametobemergedwith** , git merge --no-ff **branchnametobemerged** |
deleting remote branch| git push origin --delete **branchname**|
deleting local branch| git branch -d **branchname**|

<div id="docker"/>
#### docker

action|command|
:----:|:----:|
removing docker image|docker rmi **imagename**|
list docker images|docker images|
creating docker image|docker build -t **imagename** . |
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

<div id="k8s"/>
#### k8s

action|command|
:----:|:----:|
create a namespace object | kubectl create ns **namespacename**
create a pod object | kubectl run **podname** --image=**imagename** --port=**portnumber** --restart=Never
create a deployment object | kubectl create deploy **deployname** --image=**imagename** --port=**portnumber**
create a job object | kubectl create job **jobname** --image=**imagename**
create a cronjob object | kubectl create cj **cronjobname** --image=**imagename** --schedule="*/1 * * * *"
create a ingress object | kubectl create ing **ingressname** --rule="**domainname**/**path***=**servicename**:**portnumber**"
delete a namespace object| kubectl delete namespace **namespacename**
delete a pod object | kubectl delete po **podname**
delete a deployment object | kubectl delete deploy **deployname**
delete a job object | kubectl delete job **jobname**
delete a cron job object | kubectl delete cj **cronjobname**
delete a ingress object | kubectl delete ing **ingressname**

