# Docker volume

Create persistent data.

### Create a volume

```bash
docker volume create [volume-name]
```

### Use a volume

Mount the volume when running the docker.

```bash
docker run -dp 127.0.0.1:3000:3000 --mount type=volume,src=[volume-name]-db,target=/etc/todos [docker-name]
```

### Get info on a volume


```bash
docker volume inspect
```
