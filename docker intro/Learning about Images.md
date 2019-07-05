# Learning about images #
---
Once we create the container, images provides the environment to run the container.If we mention our image name in the docker run command it will actually map to below path.
##### Example #####
 `docker container run centos ps`

 Here the image is centos, once we run our container it will fetch the actal image for `docker-hub` registry `hub.docker.com/docker/centos:latest`.

 * `hub.docker.com`  # registry
 * `docker` # user or organization or project namespace
 * `centos` # image name
 * `latest` # tag

##### Docker image commands #####
* `docker image ls` # list all the images in your machine.
* `docker imaeg pull nginx/nginx-prometheus-exporter:0.2.0` # pull the image from docker-hub.
* `docker image history 553414f99faf` # get the history about image using image id or image name.
