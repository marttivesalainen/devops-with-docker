FROM ubuntu:latest

RUN apt-get update && apt-get install -y curl git
RUN curl --silent -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.34.0/install.sh | bash \
  && export NVM_DIR="$HOME/.nvm" \
  && [ -s "$NVM_DIR/nvm.sh" ] \
  && . "$NVM_DIR/nvm.sh" \
  && nvm --version \
  && nvm install node \
  && echo "Using latest version of Node $(node --version)" \
  && echo "Using latest version of NPM $(npm --version)"