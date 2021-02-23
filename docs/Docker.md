## Docker
On my journey, I learned that my organization makes use of Docker often. Here are my notes on the tool.

## Why use it ?
Sometimes OS’s and services are not compatible which leads to issues libraries , OS, & dependencies that will not work together.

Docker runs components, dependencies in its own containers. Just had to build the docker configuration once. 

Containers are completed isolated environments, they can have their own network interfaces, etc but they all share the same OS kernel. 

Docker uses LXC containers. 

OS have two things, an OS kernel and a set of software. The OS kernel interacts with the underlying hardware. Its the software above the OS kernel that makes them different. Could have different compilers, user interface etc.

Sharing the underlying kernel, what does that mean? Docker can run any flavor of OS so long as they are all based on the same kernel. 

Each docker container has the additional software that makes these OS's different. 

You will not be able to run a window based container with an Linux OS kernel. 

When you install Docker on windows you work Linux  container on Linux virtual machine on windows. 

Unlike hyper visors, Docker not meant to run different OS's, dockers package and ship them anywhere any time as many times as we want.

Docker installs on the OS. 

## Containers VS Virtual Machines

Utilization is used higher disk space, CPU space when you use a virtual machine. Docker allows it to boot up in seconds.

Docker has less isolation as more resources are shared. 


You can see Docker hosted on virtual docker.

Products are containerized.  

If you need to run multiple you could, you just need to remember to add a front load balancer. If one fails you can delete it and re-download it.

  ## How to Use Docker?
  There is a dockerhub or dockerstore. Where you can use `docker run [REGISTRY PRODCUT NAME]`


   ex: `docker run ansible`

    
## Container VS Image

An image is a package or template, like a VM template that is used to create one or more containers that are running instances of images that are isolated and have their own enviornments & set of processes. 

You can create your own Docker image and push it to the docker repository.

## Developers & Ops
In the past Developers would create the requirements and a set of instructions on how hosts must be set up, what prerequists are to be installed on the host and how the dependencies are to be configured, etc.  

OPs teams would hit issues as they did not develop, so working with developers to resolve. With docker the operations and developers team work together to transform the guide into a docker file with both of their requirements.The image can now run on any host, and it will work anywhere when deployed in production.

## Getting Started 
Docker has two editions, community (free docker products), Enterprise (paid products). 

Community is available on cloud platforms and on all major OS (Linux, Mac,Windows). If on Windows/OS you will have to run a virtual machine for Linux. 

### Install 
Go [here](https://docs.docker.com/engine/install/debian/) I installed using the convientient script. 

`$ curl -fsSL https://get.docker.com -o get-docker.sh`

 `$ sudo sh get-docker.sh`

With the following command I am pullling an image from dockerup called whalesay

` sudo docker pull docker/whalesay`

To run this image I ran

`sudo docker run docker/whalesay cowsay [INPUT]`

(insert my hi Txu photo here)




 ## Docker Commands 
 `docker run` runs a container from an image 

 If the image is not found it will pull the image from Docker hub, for the first time.

 `docker ps` lists all the containers that are running some basic information about them- name, container ID, names, ports and status. Each container gets a random name and ID. 


`docker ps -a  ` lists all the containers including previously stopped or exited containers. 

`docker stop [CONTAINER ID OR CONTAINER NAME]` will stop the running container.

`docker rm [CONTAINER ID OR CONTAINER  NAME]` will remove the docker container compeltely. 

`docker images` lists available images and their sizes 


`docker rmi [IMAGE NAME]` removes the images, but you must stop and remove all dependent container before it can be removed.

`docker pull [IMAGE]` only pull the image and not run the container

containers are not meant to host OS's, they are designed to carry computations or run the images. A container only lives as long as the process is alive inside.

`docker exec [IMAGE NAME] [COMMAND]` will run a command within the container.

`docker run -d [IMAGE NAME]` will run the container detached.
