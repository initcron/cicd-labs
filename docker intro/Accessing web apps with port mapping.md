# Accessing web apps with port mapping #
---
Once we create the docker container for our application, then accessing that we need to mapp application port with our localhost port.
> `docker container run -idt -p 8080:80 nginx`
* `-p`-> option for port mapping
* `8080`-> localhost port
* `80` -> application port

To access that appication on your browser visit `localhost:8080`.

Autmatically create the port mapp use `-P` insted of `-p`.
> `docker container run -idt -P nginx`
* `-P` -> automatically fetches the application port and mapp to localhost
* `docker ps -n 2 ` -> it will show mapped port

`example:-` we can access the application on `localhost:32769`
