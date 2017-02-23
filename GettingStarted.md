# Getting Started

Basic

 * Install Docker software for your platform
 * Run a software image in a container
 * Create your own image and run it in a container
 

### Install Docker software for your platform

###### Windows:
https://download.docker.com/win/stable/InstallDocker.msi

###### Linux:


Log into your Ubuntu installation as a user with sudo privileges.

Verify that you have curl installed.

 	$ which curl

If curl isn’t installed, install it after updating your manager:

     $ sudo apt-get update
     $ sudo apt-get install curl

Get the latest Docker package.

 	$ curl -fsSL https://get.docker.com/ | sh


###### Verify : 
$ docker version // show the version of docker
$ docker ps -a // show all containers on the system
$ docker images // show images

### Run a software image in a container

	$ docker run hello-world

docker - tell ur OS that u r using docker

run - subcommand that creates and run container

hello-world - tell docker to which image to load on container

A Docker image, though, is capable of much more. An image can start software as complex as a database, wait for you (or someone else) to add data, store the data for later use, and then wait for the next person.

To Run:

	$ docker run hello-world

1. checked to see if you had the hello-world software image
2. downloaded the image from the Docker Hub
3. loaded the image into the container and “ran” it

### Create your own image and run it in a container

Sample cowsay example

1. Create a file with name Dockerfile
	```
      FROM docker/whalesay:latest
      RUN apt-get -y update && apt-get install -y fortunes
      CMD /usr/games/fortune -a | cowsay
      ```
      $ docker build -t docker-whale . //command to build image
      
      $ docker images .. check image created on the system
      
      $ docker run docker-whale // run it
