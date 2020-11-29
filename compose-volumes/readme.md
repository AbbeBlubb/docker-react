# docker-compose

## About

- Containerized project up and running with just one command
- React project in Docker container in network 
- The host volume enables the hot reload
- The anonymous volume in the named volume enables the container to keep the node_modules folder so that the host doesn't need it. Therefore, the npm dependencies are not needed in the host

## Build image, tag image & start container in network

```bash
docker-compose up
docker-compose up -d
```
