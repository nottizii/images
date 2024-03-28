FROM ubuntu:latest

RUN apt-get update && apt-get install -y curl

RUN useradd -ms /bin/bash container
USER container
WORKDIR /app
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

RUN export NVM_DIR="$HOME/.nvm" && \
    [ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" && \
    [ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion" && \
    nvm install 20 && \
    npm install yarn &&\
    npx yarn

COPY . .

CMD ["/bin/bash"]

LABEL author="nottizii"
LABEL org.opencontainers.image.description DESCRIPTION
LABEL version="1.1"