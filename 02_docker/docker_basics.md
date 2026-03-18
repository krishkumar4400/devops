docker run -it ubuntu

<!-- List all the running container -->
docker ps

<!-- docker ps - -->
  -a, --all     Show all containers (default shows running)
Aliases:
  docker container ls, docker container list, docker container ps, docker ps

<!-- do more with docker ps -->
docker ps --help

<!--  List images -->
docker images

<!-- to check docker version -->
docker version

docker info

<!-- docker run --help -->

<!-- create and run a new container from an image -->
docker run -it ubuntu(image)

<!-- to pull or download only an image for future purposes -->
docker pull image-name
