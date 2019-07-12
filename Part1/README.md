# Part 1

From this README you'll find all my answers to the exercises of part 1. Some exercises are also stored in their own directories with Dockerfiles and/or additional information. However you should be able to check my answers from this README.

## Part 1.1

CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES

a1b730915024 nginx "nginx -g 'daemon of…" 14 seconds ago Up 13 seconds 80/tcp wonderful_wescoff

3d9a2edd43b9 nginx "nginx -g 'daemon of…" 18 seconds ago Exited (0) 2 seconds ago relaxed_banach

1aa789e34b2d nginx "nginx -g 'daemon of…" About a minute ago Exited (0) 2 seconds ago laughing_borg

## Part 1.2

docker ps -a

CONTAINER ID IMAGE COMMAND CREATED STATUS PORTS NAMES

docker images

REPOSITORY TAG IMAGE ID CREATED SIZE

## Part 1.3

docker run -it devopsdockeruh/pull_exercise

Give me the password: basics

You found the correct password. Secret message is:

"This is the secret message"

## Part 1.4

docker run -d --name test devopsdockeruh/exec_bash_exercise

docker exec -it test bash

tail -f ./logs.txt

Secret message is: "Docker is easy"

## Part 1.5

docker run -d -it --name ubuntu ubuntu

docker exec -it ubuntu bash

root@09a8faf32492:/# apt-get update

root@09a8faf32492:/# apt-get install curl

root@09a8faf32492:/# read escape sequence

docker exec -it ubuntu sh -c 'echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;'

Input website:

helsinki.fi

Searching..

```
!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## Part 1.6

See [Dockerfile](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part1/1.6)

```
FROM devopsdockeruh/overwrite_cmd_exercise

WORKDIR /usr/app
COPY . .
RUN node index -c 0

CMD ["/bin/bash"]
```

## Part 1.7

See [Dockerfile](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part1/1.7)

```
FROM ubuntu

WORKDIR /usr/app
COPY . .
RUN apt-get update && apt-get install -y curl

CMD ["/bin/bash"]
CMD echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;
```

## Part 1.8

See [Log file and README](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part1/1.8)

touch logs.txt

docker run -v \$PWD/logs.txt:/usr/app/logs.txt devopsdockeruh/first_volume_exercise

## Part 1.9

docker run -p 80:80 devopsdockeruh/ports_exercise

## Part 1.10

See [Dockerfile and README](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part1/1.10).

```
FROM node:alpine

EXPOSE 5000
WORKDIR /usr/app
COPY . .

CMD npm start
```

docker build -t frontend-example-docker .

docker run -p 5000:5000 frontend-example-docker

## Part 1.11

See [Dockerfile and README](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part1/1.11)

First clone or download [this repo](https://github.com/docker-hy/backend-example-docker) and follow the installing instructions.

Place the Dockerfile in the root of project and run

```
docker build -t backend-example-docker .
docker run -p 8000:8000 -v $PWD/logs.txt:/usr/app/logs.txt backend-example-docker
```

## Part 1.12

See [Dockerfile and README](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part1/1.12)

First clone or download [this](https://github.com/docker-hy/backend-example-docker) and [that](https://github.com/docker-hy/frontend-example-docker) and follow the installing instructions from both projects.

Place the Dockerfiles (backend & frontend) in the roots of corresponding projects and run:

```
docker build -t backend-example-docker .
docker run -p 8000:8000 -v $PWD/logs.txt:/usr/app/logs.txt backend-example-docker
```

```
docker build -t frontend-example-docker .
docker run -p 5000:5000 frontend-example-docker
```
