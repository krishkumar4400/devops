FROM node:20.20-alpine3.22

WORKDIR /home/app

COPY package*.json ./
COPY tsconfig*.json ./

RUN npm install

COPY src ./src

RUN npm run build

CMD [ "node", "dist/index.js" ]

