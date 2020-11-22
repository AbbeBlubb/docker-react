# Volumes

https://mherman.org/blog/dockerizing-a-react-app/



## Without docker-compose

### Build
```
- docker build -t experimental:volumes .
```

### Run
```
docker run \
    -it \
    --rm \
    -v ${PWD}:/app \ // .:/app
    -v /app/node_modules \ // Container node_modules folder not mapped to host, so host can remove the node_modules folder
    -p 3001:3000 \
    -e CHOKIDAR_USEPOLLING=true \
    experimental:volumes
```