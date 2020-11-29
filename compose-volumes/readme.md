# docker-compose

## About

- Run the React project in a Docker container
- The host volume enables the hot reload
- The anonymous volume in the named volume enables the container to keep the node_modules folder so that the host doesn't need it. Therefore, the npm dependencies are not needed in the host

## Build image, tag image & start container in network

```bash
docker-compose up
docker-compose up -d
```
