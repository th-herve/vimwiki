# Docker volume

Create persistent data.

### Create a volume

```bash
docker volume create [volume-name]
```
> can also be created automatically by docker if needed

### Use a volume

Mount the volume when running the docker.

```bash
docker run --mount type=volume,src=[ volume-name ],target=/etc/todos [ docker-name ]
#or
docker run -v [ volume-name ]:[ containerPath ] [ docker-name ]
```

### List volumes on the host

```bash
docker volume ls
```

### Get info on a volume

```bash
docker volume inspect [ volumeName ]
```

### Delete

```bash
docker volume rm [ volumeName ]
```

