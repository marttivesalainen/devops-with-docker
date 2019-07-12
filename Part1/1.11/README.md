## Part 1.11

First clone or download [this repo](https://github.com/docker-hy/backend-example-docker) and follow the installing instructions.

Place the Dockerfile in the root of project and run

```
docker build -t backend-example-docker .
docker run -p 8000:8000 -v $PWD/logs.txt:/usr/app/logs.txt backend-example-docker
```
