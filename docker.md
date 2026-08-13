# Docker Cheatsheet

Quick Docker commands for containers, images, volumes, and Compose.

## Containers

```sh
# Running containers
docker ps

# All containers
docker ps -a

# Start
docker start <container>

# Stop
docker stop <container>

# Restart
docker restart <container>

# Remove
docker rm <container>
```

## Run

```sh
docker run <image>

# Interactive
docker run -it <image> sh

# Detached
docker run -d <image>

# Name container
docker run --name app <image>

# Port mapping
docker run -p 8080:80 <image>

# Remove container automatically when it exits
docker run --rm <image>
```

## Images

```sh
docker images

docker pull <image>

docker rmi <image>

docker build -t myapp .
```

## Logs

```sh
docker logs <container>

docker logs -f <container>

docker logs --tail 100 <container>
```

## Execute Commands

```sh
docker exec <container> <command>

docker exec -it <container> sh

docker exec -it <container> bash
```

## Inspect

```sh
docker inspect <container>

docker stats

docker top <container>
```

## Volumes

```sh
docker volume ls

docker volume create data

docker volume inspect data

docker volume rm data
```

Mount a volume:

```sh
docker run -v data:/app/data <image>
```

## Networks

```sh
docker network ls

docker network create mynetwork

docker network inspect mynetwork

docker network rm mynetwork
```

## Docker Compose

```sh
docker compose up

docker compose up -d

docker compose down

docker compose ps

docker compose logs

docker compose logs -f

docker compose build

docker compose pull
```

## Cleanup

```sh
# Remove stopped containers
docker container prune

# Remove unused images
docker image prune

# Remove unused resources
docker system prune
```

Be careful with cleanup commands, especially when adding `-a` or volume-related options.
