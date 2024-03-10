# Docker basics

## Create a container

1. Create a `Dockerfile` in a project directory
2. Edit the dockerfile:

```dockerfile
# syntax=docker/dockerfile:1

FROM node:18-alpine
WORKDIR /app
COPY . .
RUN yarn install --production
CMD ["node", "src/index.js"]
EXPOSE 3000
```

3. Build the image
 
```bash
docker build -t [container-name] .
```

## Runing a container

```bash
docker run -dp 127.0.0.1:3000:3000 [container-name]
```
### List running containers

```bash
docker ps
```

## Updating a container

1. Make change in the code 
2. Stop the container: `docker stop <container-id>`
3. Delete the old container: `docker rm <container-id>`
4. Start the new one: `docker start -dp 127.0.0.1:3000:3000 [container-name]`
