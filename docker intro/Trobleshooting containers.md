# Trobleshooting containers #
---
Here we use `docker logs` and `docker exec` for troubleshooting docker containers.
use `docker ps` to find out running containers.
> `docker ps`

Use below command to find out purticular container logs,for finding logs you can use `container id` or `container name`.
> `docker logs 09f7` or  `docker logs redis`

you can follow the logs using `-f` option.
> `docker logs -f redis`

`docker exec` allows you to run a command inside a container.
> `docker exec -it redis sh`
