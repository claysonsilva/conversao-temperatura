FROM ubuntu
RUN apt update -y && \
    apt install curl -y && \
    curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash && \
    export NVM_DIR="$HOME/.nvm" && \
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm && \
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion && \
    nvm install 20 && \
    node -v && \
    npm -v
WORKDIR /home/aplicacao
COPY . .
RUN npm install package.json
ENTRYPOINT [ "node", "server.js" ]