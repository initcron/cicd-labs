# Launching your first containers #
---

 check docker version after installation using below command.

>`docker version`

 you could further validate docker by running docker run. It will run small smoke test container

>`docker run hello-world`

 use docker hub image to run a container. you can use both `docker container run` and `docker run` command for runnig a container.

 `docker container run centos ps` or `docker run centos ps`,here we are ruuning `ps` command after launching the container.
#### Example:-####
```
docker container run centos uptime
docker container run centos uname -a
docker container run centos free
```
To check the docker events you can run the `docker system events` command while you create a container. It will show all the events while creating container.

To check last run container use `docker ps -l` even it stop.you can list the number of containers by using `ps` command, some of the examples are listed below.
```
docker ps -l
docker ps -n 2
docker ps -n 3
```
 To list all the containers use `docker ps -a`.
