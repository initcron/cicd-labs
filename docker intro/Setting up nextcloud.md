# Setting up  nextcloud #
---
Here we will going to setup nextcloud using docker-hub official image.
follow the below procedure to setup nextcloud locally.

> `docker container run -idt -P -v nextcloud:/var/www/html nextcloud`
* `-v` # option for creating and mounting volume inside the container.
* `nextcloud:/var/www/html` # creating volume and mounting inside the container.

Use below commands to get running container port and logs.
```
* docker ps
* docker logs ac69
* docker logs -f ac69
```
`Example:` you can visit the application buy using `localhost:32771` on your browser.
