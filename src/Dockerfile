FROM ubuntu
WORKDIR /home/aplicacao
COPY . .
RUN apt update -y && \
    apt install curl -y && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash
RUN echo "listando diretório root" && \
    ls -la /root && \
    echo "listando diretório nvm" && \
    ls -la /root/.nvm/
ENV NVM_DIR="$HOME/.nvm" 
RUN . "$NVM_DIR/nvm.sh" && \
    . "$NVM_DIR/bash_completion" && \
    nvm install 20 && \
    npm install package.json
ENTRYPOINT [ "node", "server.js" ]