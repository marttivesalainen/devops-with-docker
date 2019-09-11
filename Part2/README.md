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

Dockerfiles, docker-compose.yml and instructions [here](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.3). Somehow I got distracted with this task so the project structure isn't quite neatiestestest. Anyway, I'm not going to fix it since it works.

```
version: '3.5'

services:
  frontend:
    build:
      context: .
      dockerfile: Dockerfile-frontend
    ports:
      - 5000:5000

  backend:
    build:
      context: .
      dockerfile: Dockerfile-backend
    ports:
      - 8000:8000

```

## Part 2.4

[Project files](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.4)

And run `docker-compose up -d --scale compute=3`

## Part 2.5

[docker-compose.yml](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.5)

```
version: '3.5'

services:
  backend:
    links:
      - redis
    build: .
    ports:
      - 8000:8000
    environment:
      - REDIS=redis

  redis:
    image: redis

```

## Part 2.6

[docker-compose.yml](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.6)

```
version: '3.5'

services:
  backend:
    build: .
    ports:
      - 8000:8000
    environment:
      DB_USERNAME: ankka
      DB_PASSWORD: lapainen
      DB_HOST: db
    depends_on:
      - db

  db:
    image: postgres
    restart: unless-stopped
    environment:
      POSTGRES_USER: ankka
      POSTGRES_PASSWORD: lapainen
    volumes:
      - database:/var/lib/postgresql/data

volumes:
  database:

```

## Part 2.7

[docker-compose.yml](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.7)

```
version: '3.5'

services:
  backend:
    build: ./backend
    ports:
      - 5000:5000
    depends_on:
      - training
    volumes:
      - model:/src/model

  frontend:
    build: ./frontend
    ports:
      - 3000:3000
    depends_on:
      - backend

  training:
    build: ./training
    volumes:
      - model:/src/model
      - data:/src/data
      - imgs:/src/imgs

volumes:
  model:
  data:
  imgs:
```

## Part 2.8

[docker-compose.yml & nginx.confg](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.8)

docker-compose.yml:

```
version: '3.5'

services:
  frontend:
    build: ./frontend
    restart: always

  backend:
    build: ./backend
    restart: always

  nginx:
    image: nginx:latest
    ports:
      - 80:80
    volumes:
      - ./nginx.conf:/etc/nginx/nginx.conf
    links:
      - frontend
      - backend
    restart: always

```
