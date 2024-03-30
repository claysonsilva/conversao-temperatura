FROM ubuntu
WORKDIR /home/aplicacao
COPY . .
RUN apt update -y && \
    apt install curl -y && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
ENV NVM_DIR="/root/.nvm" 
RUN echo "Conteudo da variavel NVM_DIR 2: $NVM_DIR" && \
    . "$NVM_DIR/nvm.sh" && \
    . "$NVM_DIR/bash_completion" && \
    nvm install 20 && \
    npm install package.json && \
    echo "VERIFICANDO NODE" && \
    ls /usr/bin/ | grep node
ENTRYPOINT [ "node", "server.js" ]