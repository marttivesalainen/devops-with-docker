## Part 1.12

First clone or download [this](https://github.com/docker-hy/backend-example-docker) and [that](https://github.com/docker-hy/frontend-example-docker) and follow the installing instructions from both projects.

Place the Dockerfiles (backend & frontend) in the root of corresponding projects and run.

```
docker build -t backend-example-docker .
docker run -p 8000:8000 -v $PWD/logs.txt:/usr/app/logs.txt backend-example-docker
```

```
docker build -t frontend-example-docker .
docker run -p 5000:5000 frontend-example-docker
```
