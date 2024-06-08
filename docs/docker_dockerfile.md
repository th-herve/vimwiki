# Docker dockerfile

- `FROM`: base image

```bash
FROM alpine:latest
```
- `LABEL`: metadata

- `CMD`: default executable run by the container (can be overridden)
- `ENTRYPOINT`: like CMD but cannot be overridden

- `EXPOSE`: what port the container app is running on (metadata only, not a config)

## Command creating new layers

Those commands create a new layer. 
Less layer == better so minimize them.

- `RUN`: execute command in a new layer

- `COPY`: copies NEW files/folder from host to container

- `ADD`: like COPY but can be from a remote url
