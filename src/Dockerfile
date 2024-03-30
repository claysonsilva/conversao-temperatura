FROM node:20.12.0-alpine3.19
WORKDIR /home/aplicacao
COPY . .
RUN npm install
EXPOSE 8080
ENTRYPOINT [ "node", "server.js" ]