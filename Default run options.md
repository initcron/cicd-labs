# Default run options#
---
Here we use default run options to run the container in the background.

>`docker run -it centos bash`
* `-i`-> used for interact with container
* `-t`-> used for sudo terminal

`docker run --rm -it alpine sh` it will create the container and remove the container once we stop that container.

To run the container always in the background, we need to use `-d` option. It will run the container in detach mode.

>`docker run -idt alpine sh`  

we can name the container buy using `--name` option while creating docker container.
> `docker container run -idt --name redis redis:alpine`
