# Docker with volumes

https://mherman.org/blog/dockerizing-a-react-app/

## About

- Run the React project in a Docker container
- The host volume enables the hot reload
- The anonymous volume in the named volume enables the container to keep the node_modules folder so that the host doesn't need it. Therefore, the npm dependencies are not needed in the host


## Without docker-compose

### Build & tag image
```
docker build -t experimental:volumes .
```

### Run image with options
```
docker run \
-it \
--rm \
-v ${PWD}:/app \
-v /app/node_modules \
-p 3001:3000 \
-e CHOKIDAR_USEPOLLING=true \
experimental:volumes
```

- docker run
- -it \
    - interactive process flag
    - pseudo-TTY flag
- --rm \
    - removes the container and volumes after the container exits
- -v ${PWD}:/app \ 
    - Or just .:/app
    - Host volume
    - To mount host-folder . to container folder build-context/app
- -v /app/node_modules \ 
    - Anonymous volume
    - Container node_modules folder not mapped to host, so host can remove the node_modules folder
- -p 3001:3000 \
    - Port mapping host:container
- -e CHOKIDAR_USEPOLLING=true \
    - Needed for hot reload
- experimental:volumes
    - Image tag name
