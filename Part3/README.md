# Part 3

From this README you'll find all my answers to the exercises of part 3. Some exercises are also stored in their own directories with related files and/or additional information. However you should be able to check my answers from this README.

## 3.1

[Documentation](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part3/3.1)

## 3.2

[Dockerfile and README](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part3/3.2)

```
FROM ubuntu:16.04

ENV LC_ALL=C.UTF-8

RUN apt-get update && \
  apt-get install -y \
  git rtmpdump wget ffmpeg python3-dev python3-setuptools \
  python3-crypto python3-requests python3-lxml \
  php-cli php-curl php-xml php-bcmath python3-pip && \
  pip3 install --user --upgrade yle-dl && \
  rm -rf /var/lib/apt/lists/* && \
  export PATH=$PATH:$HOME/.local/bin

WORKDIR /app

ENTRYPOINT ["/root/.local/bin/yle-dl"]
```
