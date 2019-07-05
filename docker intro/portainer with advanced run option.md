# Portainer with advanced run option
---
Here we will launch and practice more advanced run option by using portainer application without using docker-hub image.

Firts create a volume before running a container and validate.
> `docker volume create portainer_data`

Validate the volume and inspect the volume by using below command.
```
 docker volume ls     # list the volume.
 docker volume inspect portainer_data  # inspect the volume.
 ```
After creating the volume just run the `docker run` command along with the volume which we are created.
>`docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer`

You will just need to access the port 9000 of the Docker engine where portainer is running using your browser.
`example:- localhost:9000`
