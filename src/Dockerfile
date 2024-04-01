FROM node:20.12.0-alpine3.19
WORKDIR /home/aplicacao
COPY package*json .
RUN npm install
COPY . .
EXPOSE 8080
ENTRYPOINT [ "node", "server.js" ]