# Stop, remove and cleanup #
---
Here we will learn how to stop, remove and cleanup the containers which we are created.

#### Commands and uses:-####
> * `docker ps` # To list the containers.
* `docker pause ac69` # used for pause the container or process.
* `docker container unpause ac69` # again restart the paused container.
* `docker stop b584` # stop purticular container.
* `docker stop b584 84e6 e4da` # stop multiple containers using single command.
* `docker ps -a` # To list all the containers including stoped containers.
* `docker start redis` # start the stoped container.
* `docker rm -f b584` # remove the container.
* `docker container prune` # It will delete all the stoped containers.
* `docker system purne` # It will remove all stoped containers and dangling images.
* `docker image rm 4206` # remove purticular image locally.
* `docker image rm 4f1 4d9 4c1 9f3` # delete multiple images.
* `docker system info` # list the detail of all the containers, images.
