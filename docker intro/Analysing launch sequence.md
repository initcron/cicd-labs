# Analysing launch sequence #
___
### Step by step process of the docker container run###
Once we run our container below events will run in the background.
* docker image pull
* docker container create
* docker container start

once we start the container, it actually runs the application inside the container. `docker container run` is the combination of all the above three events.
