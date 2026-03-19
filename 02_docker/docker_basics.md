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

<!-- docker cli -> used to interact with docker by running docker commands -->

<!-- commands related to docker image -->

<!-- delete an image -->
docker image rm alpine

<!-- but first we have to remove container using that image -->
docker container rm container_id

<!-- list all the images -->
docker image ls, docker images

<!-- remove all the pruned or unused images -->
docker image prune

<!-- pull or download an image -->
docker image pull alpine

<!-- commands related ot  docker container  -->
# docker container --help

# docker run --help

<!-- 1. list all the containers -->
docker ps -a

<!-- list only running containers -->
docker ps, docker container ls

<!-- stop running of a container -->
docker kill container_id

<!-- create and run container also specify name because docker gives default random name -->
docker run -it --name my-container alpine

<!-- remove a container -->
docker rm id, docker container rm id

<!-- remove running container -->
 docker rm --force 7daec13b5981,  docker rm -f 9c72c76b014d

#

docker run -it ubuntu ls
docker run -it ubuntu bash
docker run -it busybox ping google.com
docker run -it busybox - by default it goes inside sh (shell)
docker image inspect busybox

<!-- Creating and Using a Dockerfile to Containerize Node.js App -->
docker build -t my-app .
docker images
docker run -it my-app

# pwd to check the current dorectory

cat index.js
npm start
