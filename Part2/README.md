# Part 2

From this README you'll find all my answers to the exercises of part 2. Some exercises are also stored in their own directories with docker-compose files and/or additional information. However you should be able to check my answers from this README.

## Part 2.1

```
version: '3'

services:
  first_volume_exercise:
    image: devopsdockeruh/first_volume_exercise
    volumes:
      - ./logs.txt:/usr/app/logs.txt
```
