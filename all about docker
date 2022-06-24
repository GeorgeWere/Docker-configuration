---
title: "All about Docker Containers & images"
author: ["George", "PSNadmin"]
date: 24/6/2022
subject: "Docker Containers"
subtitle: "Usefull docker commands"
lang: "en"
titlepage: true
code-block-font-size: \scriptsize
---

# Docker containers & images

## Introduction

A Docker container image is a lightweight, standalone, executable package of software that includes everything needed to run an application: code, runtime, system tools, system libraries and settings.

## Some of the Usefull commands You should know

### Install Docker

The first thing you need to do is to set up a system with the requirements needed to run Docker and Docker compose. Then install Docker and Docker compose if you don’t have them already.

### Install Docker Engine

On Ubuntu/Debian

```bash
curl -sSL https://get.docker.com/ | sh
```
Then

```bash
systemctl start docker
```

On Centos

```bash
 yum install -y yum-utils
 yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
 yum install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

If you would like to use Docker as a non-root user, you should now consider adding your user to the docker group with something like the following command (remember that you’ll have to log out and log back in for this to take effect):

```bash
usermod -aG docker your-user
```

### Docker compose

Docker Compose 1.29 or newer is required. Follow these steps to install it

Download the Docker Compose binary:

```bash
curl -L "https://github.com/docker/compose/releases/download/1.29.2/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```

Grant execution permissions:

```bash
chmod +x /usr/local/bin/docker-compose
```

**Note If the command docker-compose fails after installation, check your path. You can also create a symbolic link to /usr/bin or any other directory in your path.**

```bash
ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

Test the installation to ensure everything went properly:

```bash
 docker-compose --version
```

### Remove Docker Images

#### Docker rmi

docker rmi removes images by their ID.

To remove the image, you first need to list all the images to get the Image IDs, Image name and other details. By running simple command 

```bash
docker images -a
```
or

```bash
docker images
```

After that you make sure which image want to remove, to do that executing this simple command

```bash
docker rmi <your-image-id>
```

Then you can confirm that image has been removed or not by list all the images and check.

#### Remove multiple images

There is a way to remove more than one images at a time, when you want to remove multiple specific images. So to do that first get Image IDs simply by listing the images then execute simple followed command.

```bash
docker rmi <your-image-id> <your-image-id> ...
```

Write Images IDs in the command followed by the spaces between them.

#### Remove all images at once

To remove all images there is a simple command to do that. 

```bash
docker rmi $(docker images -q)
```

Here in the above command, there are two command the first which execute in the **$()** is shell syntax and returns the results whatever executed in that syntax.

So in this -q- is a option is used to provide to return the unique IDs,$() returns the results of image IDs and then docker rmi removes all those images removes all those images.

#### Docker rm

docker rm removes containers by their name or ID.

When you have Docker containers running, you first need to stop them before deleting them.

- Stop all running containers: docker stop $(docker ps -a -q)
- Delete all stopped containers: docker rm $(docker ps -a -q)

#### Remove multiple containers

You can stop and delete multiple containers by passing the commands a list of the containers you want to remove. The shell syntax $() returns the results of whatever is executed within the brackets. So you can create your list of containers within this to be passed to the stop and rm commands.

##### Here is a breakdown of docker ps -a -q

- docker ps list containers
- *-a* the option to list all containers, even stopped ones. Without this, it defaults to only listing running containers
- *-q* the quiet option to provide only container numeric IDs, rather than a whole table of information about containers
