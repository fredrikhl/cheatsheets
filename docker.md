# Docker

## Run an image

```bash
# Run the Dockerfile CMD
docker run <image_name>

# Interactive bash, and remove container afterwards
docker run -it --rm <image_name> /bin/bash

# Port mapping
docker run -it -p <host>:<container> <image_name>
```


## Run something in an existing, running container

```bash
# Requires docker>=1.3
docker exec -it <container_name> bash
```


## Inspect

```bash
# inspect a running container
docker inspect <container_name> (or <container_id>)

# Get the process ID for a container
# Source: https://github.com/jpetazzo/nsenter
docker inspect --format {{.State.Pid}} <container_name_or_ID>

# List the current mounted volumes for a container (and pretty print)
# Source:
# http://nathanleclaire.com/blog/2014/07/12/10-docker-tips-and-tricks-that-will-make-you-sing-a-whale-song-of-joy/
docker inspect --format='{{json .Volumes}}' <container_id> | python -mjson.tool
```


## Cleanup

```bash
# Cleanup exited processes:
docker rm $(docker ps -q -f status=exited)

# Cleanup dangling volumes:
docker volume rm $(docker volume ls -qf dangling=true)

# Cleanup dangling images:
docker rmi $(docker images --filter "dangling=true" -q --no-trunc)
```
