FROM ubuntu
WORKDIR /home/aplicacao
COPY . .
RUN apt update -y && \
    apt install curl -y && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
ENV NVM_DIR="/root/.nvm" 
RUN . "$NVM_DIR/nvm.sh" && \
    . "$NVM_DIR/bash_completion" && \
    nvm install 20 && \
    echo "INSTALANDO DEPENDENCIAS" && \
    npm install && \
    echo "VERIFICANDO NODE" && \
    ls /usr/bin/ | grep node
ENTRYPOINT [ "node", "server.js" ]