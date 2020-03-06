FROM node:12.13.0-alpine 
EXPOSE 3000
WORKDIR /app
COPY  . .
#RUN npm install

RUN  yarn install --network-concurrency 1



CMD ["yarn", "start"]