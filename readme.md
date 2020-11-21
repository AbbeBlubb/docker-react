# Volumes

https://mherman.org/blog/dockerizing-a-react-app/

### Build
- docker build -t experimental:volume .

### Run
docker run \\\
    -it \\\
    --rm \\\
    -v ${PWD}:/app \\\
    -v /app/node_modules \\\
    -p 3001:3000 \\\
    -e CHOKIDAR_USEPOLLING=true \\\
    experimental:volume
