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

```<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="http://www.helsinki.fi/">here</a>.</p>
</body></html>
```

## Part 1.9

docker run -p 80:80 devopsdockeruh/ports_exercise
