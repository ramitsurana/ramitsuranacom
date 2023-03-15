---
title: Introducing Turbo for Docker
publishDate: 2016-09-01 00:00:00
img: /assets/stock-4.jpg
description: Creating Turbo for use with Docker
tags:
  - Docker
  - Containers
  - Golang
---

Minasan, kon'nichiwa (Japense)(In English - Hello Friends). Hope you folks are having an awesome day at work ! For the past sometime I have been learning and exploring golang.It is an awesome language becoming popular like python and java.Following the reason to implement golang in some of my project's.I started to implement golang and try golang in the most efficient manner as possible.This year I decided to start this project following my process of learning.As much like as every developer I Hope you find them useful and worth contributing.


## Turbo

One of the most popular container projects in the market is [Docker][1].It has been in the market for very less no. of years.But has gained popularity like nothing else in the market.Since the introduction of [Docker][1] project containers have been continously gaining momentum and recognition than before.With time the current methodologies to build containers have been changing and replacing with time.

[Turbo][2] is a simple yet powerfull utility for [Docker][1].The main aim for designing [turbo][2] main focus is to introduce simplicity,automate the current process to build a flexible enviorment and to make [docker][1]  usage like never before.[Turbo][2] implements simple and regularly used useful commands on a currently installed [docker][1] enviorment.It is written in [golang][6].This makes it more compatible with [docker][1].It is lightweight in nature which makes it awesome to use and can be deployed wherever you want.

![turbo1](https://cloud.githubusercontent.com/assets/8342133/16713587/95b469bc-46ca-11e6-8fb3-e56c7ce7d19d.png)

## Why Turbo ?

The real answer to this question is curiosity.I think as a regular docker user myself I wanted to experience some new tools and functionalities with docker.Although I agree,that docker has a beautiful cli that provides almost everything you need to play with containers.But, I guess having everything is never enough.Haha.So I began enjoying adding more options that makes it easy to use and adopt docker in a more useful and interactive manner.Although the journey has just begun.There's a lot to be done. 


## Getting Started 

There are multiple ways to started using Turbo.For the normal users,

Go to [releases](https://github.com/ramitsurana/turbo/releases) sections of the turbo's github repo.
Install the tar file.
Untar it.

````
$ cp turbo /usr/local/bin
````
Try it out using

````
$ turbo
````
If everything is correctly done you should get output something like this:

````
Turbo:
  Simple and Powerfull utility for Docker

Usage:
  Turbo [command]

Available Commands:
  backup      backups all your docker stuff
  clean       Cleans up all your docker images
  destroy     Erases off all the exited containers
  harbor      installs and configures vmware harbor
  kickstart   restarts all your containers quickly
  kube        Installs and configure minikube for your system
  ldap        Uses to install and configure Openldap
  log         Uses logspout to collect your docker logs
  monitor     To monitor your containers
  proxy       Installs and configure squid3 proxy for your system
  refresh     Completely removes and re-installs docker
  replica     To create Replicas of your containers
  rkt         Installs and configures rkt
  search      Search images from multiple registries
  ship        Transfer your docker images over a remote i.p.
  version     prints the current version number of turbo

Flags:
      --config string   config file (default is $HOME/.turbo.yaml)
  -h, --help            help for Turbo
  -t, --toggle          Help message for toggle

Use "Turbo [command] --help" for more information about a command.

````
For people working on golang,they can start using it via

````
$ go get -v github.com/ramitsurana/turbo
````

## Using Turbo

Turbo works on a simple command line based model where you can use the commands built by turbo in a simple and easy to use manner.
Some of the commands used are:

* [Backup](#backup) - Backups all your stuff so that you can have a copy in case anything goes wrong.
* [Clean](#clean) - Wipes of all your [docker][1] images from your system.
* [Destroy](#destroy) - Kills all of your exited containers.
* [Kickstart](#kickstart) - Restarts all your containers
* [Log](#log) - Installs and configures logspout on your system
* [Monitor](#monitor) - Helps you monitor your docker containers
* [Refresh](#refresh) - Removes Docker ecosystem and Installs a new one
* [Replica](#replica) - Creates multiple replicas of your docker container
* [Rkt](#rkt) - Installs and configures rkt on your system
* [Search](#search) - Searches Docker registry hub,quay.io for your images
* [Ship](#ship) -  Ships off all your Docker Stuff to remote <I.P>
* [Version](#version) - Displays Turbo version 
* [kube](#kube) - Installs and Configures Minikube on your system
* [Harbor](#harbor) - Installs and configures Harbor on your system
* [Proxy](#proxy) - Installs and configures squid proxy on your system
* [Ldap](#ldap) - Installs and configures Openldap on your system

## Conclusion

For me building this project has been a fun and awesome experience.Obviously like any other project there are more stuff to do,ensure ease of access and more fun features for users.In the end,I hope you enjoyed this post and you give it a shot.

  [1]: http://docker.com
  [2]: http://github.com/ramitsurana/turbo
  [3]: http://ramitsurana.github.io/turbo
  [4]: https://cloud.githubusercontent.com/assets/8342133/12071970/ed85ee72-b0ed-11e5-9a99-d4b0d8d8a36a.png  
  [6]: http://golang.org
