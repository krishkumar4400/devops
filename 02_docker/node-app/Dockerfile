# Base Image
FROM node:20.17.0-alpine3.19

WORKDIR /home/app

# Copying the source code to docker image 
COPY package-lock.json package-lock.json
COPY package.json package.json
RUN npm install

COPY index.js index.js

COPY Dockerfile Dockerfile

# if any time anyone runs this image particularly run this command.
# this will be default command that will run when a developer will run this image 
# but we can also override it using -  docker run -it my-app bash // ls, cd, pwd etc
CMD [ "npm", "start" ]
