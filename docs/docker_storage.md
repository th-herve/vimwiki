# Docker storage

Four types:

## Writable layer

File system of the container.

## Tmpfs

Fast memory, relying on the host ram.
Useful for operation that need speed or for sensitive data.

- not persistent
- can't be shared between containers

## Bind mounts

Map host folder to a container folder.

- accessible by multiple containers
- but depends on the host file structure, so less portable

```bash
docker run --name <name> --mount type=bind,source="$(pwd)"/<hostDir>,target=<containerDirPath>
#or
docker run --name <name> -v "$(pwd)"/<hostDir>:<containerDirPath>
```

## Volumes

Similar to bind mounts, but it's managed by docker. Meaning can be created if needed by the container.

[Volume](docker_volume.md)


