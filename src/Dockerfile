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
    node -v && \
    which node
ENV PATH="/root/.nvm/versions/node/v20.12.0/bin/:$PATH"
ENTRYPOINT [ "node", "server.js" ]