# Part 2

From this README you'll find all my answers to the exercises of part 2. Some exercises are also stored in their own directories with docker-compose files and/or additional information. However you should be able to check my answers from this README.

## Part 2.1

[docker-compose.yml & logs.txt](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.1)

```
version: '3'

services:
  first_volume_exercise:
    image: devopsdockeruh/first_volume_exercise
    volumes:
      - ./logs.txt:/usr/app/logs.txt
```

## Part 2.2

[docker-compose.yml & logs.txt](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.1)

```
version: '3.5'

services:
  port_exercise:
    image: devopsdockeruh/ports_exercise
    ports:
      - 80:80
```

Run `docker-compose up` and open [http://localhost](http://localhost) in your browser

## Part 2.3

Dockerfiles, docker-compose.yml and instructions here

```
version: '3.5'

services:
  frontend:
    build: ./frontend
    ports:
      - 5000:5000

  backend:
    build: ./backend
    ports:
      - 8000:8000
```
