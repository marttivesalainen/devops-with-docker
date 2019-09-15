## 3.8

This Dockerfile creates an image by which you can download a git repository with a Dockerfile, build it and push to Docker Hub.

Build the image `docker build -t foo .`

Run the image `docker run -v /var/run/docker.sock:/var/run/docker.sock -it foo [git repo] [image-tag] [docker registry]`
