## Part 1.13

First clone or download [this repo](https://github.com/docker-hy/spring-example-project).

Place the Dockerfile in the root of project and run

```
docker build -t spring-example-project .
docker run -p 8000:8000 spring-example-project
```
