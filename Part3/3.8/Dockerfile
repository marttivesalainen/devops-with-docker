FROM ubuntu:16.04

ENV LC_ALL=C.UTF-8

WORKDIR /usr/app
COPY /script /usr/app/script

RUN apt-get update && \
  apt-get install -y \
  curl \
  apt-transport-https \
  ca-certificates \
  gnupg-agent \
  software-properties-common && \
  curl -fsSL https://download.docker.com/linux/ubuntu/gpg | apt-key add - && \
  add-apt-repository \
  "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
  $(lsb_release -cs) \
  stable" && \
  apt-get update && \
  apt-get install -y \
  docker-ce \
  docker-ce-cli \
  containerd.io && \
  chmod +x script

ENTRYPOINT ["/usr/app/script"]