# Docker & React

## Dockerfile.dev
- Template for copying the project
- CMD: npm start

## docker-compose.yml
- For dev
- Uses the Dockerfile.dev template
- Service "web": the dev server
- Service "tests": the test runner (overrides the default command/CMD)

## Dockerfile
- For prod
- Uses multi-step builds: NGINX on Alpine with built project

## .travis.yml
- Dockerfile.dev for running tests
- Dockerfile for prod

## Volume issues
Problems with hot reload in mounted volumes when using Docker on Windows. Not working despite using polling etc. Solution:
- Windows 10 build 2004 with WSL2 and distro for WSL2, run docker and project from the Linux distro CLI
