## Part 1.14

First clone or download [this repo](https://github.com/docker-hy/rails-example-project).

There is no official Docker image for Ruby version 2.3.0. Ruby version is defined by default in the Gemfile so you should change it to correspond the image you are using.

Place the Dockerfile in the root of project and run

```
docker build -t spring-example-project .
docker run -p 8000:8000 spring-example-project
```
