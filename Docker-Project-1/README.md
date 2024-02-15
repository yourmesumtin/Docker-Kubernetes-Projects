## To run interactive Docker containers from terminals with Gitbash

winpty docker container run -it alpine:3.19.1 sh

## To run interactive Docker containers from terminals with Command Prompt and Mac

docker container run -it alpine:3.19.1 /bin/sh

## COMMANDS
winpty docker container run -it e4524956d245 sh  #Connect to a running container (replace 'e4524956d245' with the Container ID) FOR DOCKERFILE BUILDING AND RUNNING.

- `docker container prune` : Remove all unused containers, networks, volumes, and images not used by at least one
- `docker image ls` : List all the images on your machine.
- `docker container ls` : List all running containers.
- `docker container ps -a` : List all containers, including those not running.
- `docker start <container_id>` : Start a container that is currently stopped.
- `docker stop <container_id>` : Stop a running container.
- `docker restart <container_id>` : Restart a running container.
- `docker rm <container_id>`: Remove/Delete a stopped container.
- `docker rmi <image_id>`: Delete an unused image.
- `docker images -f "dangling=true"`: Show only images without any tags
- `docker volume ls`: List all volumes.
### Build Image From Dockerfile
- `docker  build -t <name>:<tag> .`
### Run Container From Image
- `docker run -d -p <host_port>:<container_port></br />--name <container_name> <image_name>`: Runs a new instance of the container in detached mode (in the background) and maps port(s) to
- `docker run -p <hostPort>:<containerPort> <ImageName>:<Tag>`



