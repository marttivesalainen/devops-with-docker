## Part 1.15

Docker image is available in [this public repository](https://hub.docker.com/r/marttivesalainen/hello-world-exercise).

In a nutshell, the image clones a [simple hello world application](https://github.com/marttivesalainen/node-hello-world), install its depedencies, exposes port 3000 by default and run the application.

Simply run `docker run -p 3000:3000 marttivesalainen/hello-world-exercise` and open [http://localhost:3000](http://localhost:3000) in your browser.
