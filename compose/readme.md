# docker-compose

## About

- Run the React project in a Docker container
- The host volume enables the hot reload
- The anonymous volume in the named volume enables the container to keep the node_modules folder so that the host doesn't need it. Therefore, the npm dependencies are not needed in the host

## Build & tag image

```bash
docker build -t experimental:compose .
```

## Run

```bash
docker-compose up
docker-compose up -d
```

## docker-compose ps vs docker ps

`docker ps` lists all running containers in docker engine. `docker-compose ps` must be run in context of the docker-compose file and lists containers related to images declared in docker-compose file. The result of `docker-compose ps` is a subset of the result of `docker ps`
