## Part 2.3

For the sake of clarity and because we are only interested in Dockerfiles and docker-compose.yml, I didn't want to include application repositories in my commits. If you want to see the application running you must manually clone and install [frontend](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.3/frontend) and [backend](https://github.com/marttivesalainen/devops-with-docker/tree/master/Part2/2.3/backend). Just follow the instructions in both READMEs in those subdirectories.

After you have set up the project, run `docker-compose up` in the project root.

OR

In project root run `(cd backend && git clone https://github.com/docker-hy/backend-example-docker.git . && npm install) && (cd frontend && git clone https://github.com/docker-hy/frontend-example-docker.git . && npm install) && docker-compose up`
