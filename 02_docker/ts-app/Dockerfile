# # # lighter in size
# FROM node:20-alpine as base
# # light in size
# # FROM gcr.io/distroless/nodejs20 AS base


# # State 1: Build stuff
# FROM base as builder 

# WORKDIR /home/build

# COPY package*.json ./
# COPY tsconfig*.json ./ 

# RUN npm install 

# COPY src ./src

# RUN npm run build 

# # Stage 2: Runner
# FROM base as runner

# WORKDIR /home/app

# COPY --from=builder /home/build/dist /dist
# COPY --from=builder /home/build/package*.json .

# # this basically means only install express. not dev dependencies
# RUN npm install --omit=dev

# EXPOSE 3000

# CMD [ "node", "start" ]


# # Optimized
# # # Stage 1: Builder (full Node environment)
# # FROM node:20-alpine AS builder

# # WORKDIR /home/build

# # COPY package*.json ./
# # COPY tsconfig*.json ./

# # RUN npm ci

# # COPY src ./src

# # RUN npm run build


# # # Stage 2: Runner (distroless)
# # FROM gcr.io/distroless/nodejs20

# # WORKDIR /home/app

# # COPY --from=builder /home/build/dist ./dist
# # COPY --from=builder /home/build/package*.json ./

# # # install only production deps (DO THIS IN BUILDER INSTEAD)
# # # distroless cannot run npm → so we fix this 👇

# # # better approach: copy node_modules from builder
# # COPY --from=builder /home/build/node_modules ./node_modules

# # EXPOSE 3000

# # CMD ["dist/index.js"]



# # FROM node:20-alpine AS builder

# # WORKDIR /home/build

# # COPY package*.json ./
# # COPY tsconfig*.json ./

# # RUN npm ci --omit=dev

# # COPY src ./src

# # RUN npm run build


# # FROM gcr.io/distroless/nodejs20

# # WORKDIR /home/app

# # COPY --from=builder /home/build/dist ./dist
# # COPY --from=builder /home/build/node_modules ./node_modules

# # EXPOSE 3000

# # CMD ["dist/index.js"]


FROM node:20-alpine as base

# State 1: Build stuff 
FROM base As builder 

WORKDIR /home/build 

COPY package*.json ./ 
COPY tsconfig*.json ./ 

RUN npm install 

COPY src ./src 

RUN npm run build 


# Stage 2: Runner 
FROM base AS runner 

WORKDIR /home/app 

COPY --from=builder /home/build/dist ./dist
COPY --from=builder /home/build/package*.json . 

# this basically means only install express. not dev dependencies 
RUN npm install --omit=dev 

EXPOSE 3000

CMD [ "npm", "start" ]

