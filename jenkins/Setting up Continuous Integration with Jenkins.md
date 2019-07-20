# Setting up Continuous Integration with Jenkins
Here you will learn how to run jenkins by using docker container and configure it, launching jobs, adding unit test and packaging Jobs. configuring build triggers to auto launch jenkins, defining downstream/upstream and a pipeline view. how to integrate github with jenkins to setup jenkins, configuring job status with commit messages and setting up a CI pipeline for a NodeJS app.

### Setup jenkins with docker :-
In this Lab you are going learn how to setup jenkins using docker. prerequisite for this you need docker installed locally.

You could run a jenkins container on your docker host by using official jenkins image with the version `2.178-Slim`. Use below command to run a jenkins container,
```
docker container run -idt --name jenkins -P p 8080:8080 -v jenkins_home:/var/jenkins_home -v /var/run/docker.sock:/var/run/docker.sock jenkins/jenkins:2.178-slim
```
