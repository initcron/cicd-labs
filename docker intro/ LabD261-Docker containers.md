# Lab: Getting started with docker
---
In this chapter, you will learn how to create docker containers using docker images, analysing and troubleshooting those containers by using docker commands. you will also learn how to launch application by using docker containers and advanced docker management tool portainer which help us to manage our docker resources using UI.

###  Launching your first container :-
check your docker version after installation using below command.
```
docker version
```
you could further validate docker by running docker run. It will run small smoke test container
```
docker run hello-world
```
use image form docker to run a container. you can use both `docker container run` and `docker run` command for runnig a container.

`docker container run centos ps` or `docker run centos ps`,here we are ruuning `ps` command after launching the container.

Next you have few `examples` for docker container run,
```
* docker container run centos uptime
* docker container run centos uname -a
* docker container run centos free
```
you could check your docker events by uisng `docker system events` command while you create a container. It will show all the events while creating container.

you can check your last run container using `docker ps -l` even that container in stopped state and you can list the number of containers by using `ps` command, some of the examples are listed below.
```
* docker ps -l
* docker ps -n 2
* docker ps -n 3
```
To list all the containers use `docker ps -a`.
### analysing launch sequence :-
Once you created your container by using docker container run the below events will be run while launching that container and you can easily understand the step by step process of docker container run.
```
* docker image pull
* docker container create
* docker container start
```
once you start the container, it actually runs the application inside the container. `docker container run` is the combination of all the above three events.
### Learning about images :-
Once you create your container, docker image provides the environment to run the container.If you mention your image name in the docker run command it will actually map to docker-hub registry and your docker-hub id and finally your image, here below you have a example for the image.
  * `Example:-`
 ```
 docker container run centos ps
 ```
 Here the image is centos, once you run your container it will fetch the actual image for `docker-hub` registry `hub.docker.com/docker/centos:latest`.

You could use below commands to list your images from your local machine and pull the image from docker-hub.Even you can get the history about image by using your image name or image id.
 ```
 * docker image ls
 * docker image pull nginx/nginx-prometheus-exporter:0.2.0
 * docker image history 553414f99faf
 ```
### Default run options :-
 you already know how to run a container,but here you will learn how to run a container in the background using default run options.
 ```
docker run -it centos bash
 ```
 you could use below command while creating your container, it will remove your container once you stopped it.
 ```
 docker run --rm -it alpine sh
 ```
 if you need to run your container always in background, you can use `-d` option, it will run your container in detach mode and you will name your container by using `--name` while creating your container.
 ```
 docker container run -idt --name redis redis:alpine
 ```
 ### Accessing web apps with port mapping :-
 Once you create a docker container for your application,then accessing that application on browser you need to mapp application port with our localhost port.
 ```
 docker container run -idt -p 8080:80 nginx
 ```
 once you done the port mapping, access that application on your browser by visiting `localhost:8080`.

 Above you used purticular port for port mapp with `-p`, but you can achive automatic port mapping by using `-P` while you create your container.
```
docker container run -idt -P nginx
```
once you create containe, you need port to access that application,for that use `docker ps -n 2` you will get mapped port.

`Example:-` you can access your application on `localhost:32769`.
### Troubleshooting containers :-
Here you will learn how to check log and troubleshoot containers by using below commands.

find your container id or container name using `docker ps`.

You could use below command to find out purticular container logs
```
 docker logs 09f7` or  docker logs redis
 ```

you can follow the logs using `-f` option and `docker exec` allows you to run a command inside a container.
 ```
 docker logs -f redis
 docker exec -it redis sh
 ```
 ### Setting up nextcloud :-
 previously you have some understanding about running application using containers, here you will setup nextcloud application using official image with creating volume and mounting inside the container.

 You just follow the below procedure to Setting up nextcloud.
 ```
 docker container run -idt -P -v nextcloud:/var/www/html nextcloud
 ```
 <img src="/home/mohan/gourav/261-labguide/docker intro/images/nextcloud1.png"/>

 Use below commands to get running container port and logs.
 ```
 * docker ps
 * docker logs ac69
 * docker logs -f ac69
 ```
 `Example:` you can visit the application buy using `localhost:32770` on your browser.
 <img src="261-labguide/docker intro/images/nextcloud2.png"/>
### Portainer with advanced run option :-
Here you will launch and practice more advanced run option by using portainer application.

Firts you need to create a volume before running a container and validate the volume by using below commands.
```
* docker volume create portainer_data
* docker volume ls
* docker volume inspect portainer_data
```
![](https://github.com/initcron/261-labguide/tree/master/docker%20intro/images)
 <img src="261-labguide/docker intro/images/portainer1.png"/>
 ![](../images/portainer1.png)

 After creating the volume you just run the `docker run` command along with the volume which we are created.
 ```
 docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
 ```
Once you created your container, then access the portainer application using port 9000 on your browser.

 `example:- localhost:9000`
 <img src="261-labguide/docker intro/images/portainer2.png"/>

### Stop, remove and cleanup :-
Here you will learn how to stop, remove and cleanup the containers which you have created.

Find your container id and stop the container before you are going to remove and you can pause and unpause the container as well.
```
* docker ps
* docker pause ac69
* docker unpause ac69
* docker stop b584
* docker stop b584 84e6 e4da
```
you can remove or again start the container once it stopped.
```
* docker start redis
* docker rm -f b584
```
you could remove the images which ever you want and you can also delete all the stopped containers and dangling images by using below commands.
```
* docker image rm 4206`
* docker image rm 4f1 4d9 4c1 9f3
* docker system prune
```
You could get all your docker system information by using `docker system info`.
