# Docker commands

- show running containers: `docker ps`

- show running containers history: `docker ps -a`

- list images on the machine: `docker images`

- show info on a image: `docker inspect <image>`

`docker restart <containerId>`
`docker stop <containerId>`
`docker logs <containerId>`


- show port used by a running container: `docker port <containerId>`

- run command in a container: `docker exec -it <containerId> <command>`

## run

- run a docker: `docker run <image>` (pull the image if not on the system)

to specify a port :

```bash
docker run -p <localPort>:<containerPort> <image>
```

-d detach from the shell

## Remove

A container:  
`docker rm <containerId>`

An image:  
`docker rmi <imageId>`

## Create image

`docker build -t <name> <context>`

context = path where to look for files

```bash
docker build -t docker-app1 .
```
