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

## 3.3

[Dockerfiles](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part3/3.3)

### Frontend

```
FROM ubuntu:16.04

COPY . /usr/app
WORKDIR /usr/app

RUN apt-get update && \
  apt-get install -y curl && \
  curl -sL https://deb.nodesource.com/setup_10.x | bash && \
  apt-get install -y nodejs && \
  npm install && \
  apt-get purge -y --auto-remove curl && \
  rm -rf /var/lib/apt/lists/* && \
  useradd -m app && \
  chown -R app:app /usr/app

USER app

EXPOSE 5000

CMD npm start
```

### Backend

```
FROM ubuntu:16.04

COPY . /usr/app
WORKDIR /usr/app

RUN apt-get update && \
  apt-get install -y curl && \
  curl -sL https://deb.nodesource.com/setup_10.x | bash && \
  apt-get install -y nodejs && \
  npm install && \
  apt-get purge -y --auto-remove curl && \
  rm -rf /var/lib/apt/lists/* && \
  useradd -m app && \
  chown -R app:app /usr/app

USER app

EXPOSE 8000

CMD npm start
```

## 3.4

[Dockerfiles and documentation](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part3/3.4)

```
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
backend             alpine              762917142e6e        3 minutes ago       152MB <- Alpine
frontend            alpine              762917142e6e        3 minutes ago       152MB <- Alpine
frontend            latest              8fa7998bdd6c        39 minutes ago      440MB <- Ubuntu
backend             latest              53c442d65f1a        43 minutes ago      337MB <- Ubuntu
```

## 3.5

[Dockerfile and documentation](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part3/3.5)

```
FROM node:alpine AS builder
COPY . /usr/app
WORKDIR /usr/app
RUN npm install && npm run build

FROM nginx
COPY --from=builder /usr/app/dist /usr/share/nginx/html

EXPOSE 5000
```

## 3.6

Skip.

## 3.7

### Why and when to use Kubernetes

Kubernetes is a tool used to orchestrate containers in a large multi-host application environments. As stated on Kubernetes’s official website, it takes care of applications scaling requirements, failover, deployment patterns, and more. With Kubernetes organizations may decrease their application maintenance costs signigicantly since it eliminates the need of running and managing individual VM’s or servers for each service.

E.g. a traditional deployment method such as running all micro-services on one physical server has scalability issues. To scale a service the only way is to start and/or maintain a spare physical server which is might be costly. Moreover if a service crashes, the system administrators must restart the it manually. Also end users may suffer due the service downtime during the recovery. Kubernetes however orchestrates containers automatically and can start new container instances on the fly reducing downtime.

With Kubernetes organizations can achive even more benefits than mentioned above such consistent environment across development, testing and production, portability and observability. Organizations should consider using Kubernetes rather than traditional approaches when handling multiple micro-services. The main advantages are improvements in cooperation between developers and teams due the environment consistency, agile deployment and automated operations which all reduces invested working hours and costs.
