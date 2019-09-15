# 3.4

```
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
backend             alpine              762917142e6e        3 minutes ago       152MB <- Alpine
frontend            alpine              762917142e6e        3 minutes ago       152MB <- Alpine
frontend            latest              8fa7998bdd6c        39 minutes ago      440MB <- Ubuntu
backend             latest              53c442d65f1a        43 minutes ago      337MB <- Ubuntu
```

## Backend

### Before

```
➜  frontend git:(master) docker history backend
IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
53c442d65f1a        12 minutes ago      /bin/sh -c #(nop)  CMD ["/bin/sh" "-c" "npm …   0B
b69429d4fb3f        12 minutes ago      /bin/sh -c #(nop)  EXPOSE 8000                  0B
c80400e96d9d        12 minutes ago      /bin/sh -c #(nop)  USER app                     0B
2c60fc962704        12 minutes ago      /bin/sh -c apt-get update &&   apt-get insta…   217MB
d5ee69d77650        13 minutes ago      /bin/sh -c #(nop) WORKDIR /usr/app              0B
a3e1850294ec        13 minutes ago      /bin/sh -c #(nop) COPY dir:edf29dc9a672c293e…   9.05kB
5e13f8dd4c1a        7 weeks ago         /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>           7 weeks ago         /bin/sh -c mkdir -p /run/systemd && echo 'do…   7B
<missing>           7 weeks ago         /bin/sh -c set -xe   && echo '#!/bin/sh' > /…   745B
<missing>           7 weeks ago         /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>           7 weeks ago         /bin/sh -c #(nop) ADD file:603693e48cdc7f0c5…   120MB
```

### After

```
➜  backend git:(master) ✗ docker history backend:alpine
IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
762917142e6e        2 minutes ago       /bin/sh -c #(nop)  CMD ["npm" "start"]          0B
d3a869d5b2d1        2 minutes ago       /bin/sh -c #(nop)  EXPOSE 8000                  0B
d7121a449500        2 minutes ago       /bin/sh -c npm install                          71.5MB
c3e6ca380175        3 minutes ago       /bin/sh -c #(nop) WORKDIR /usr/app              0B
0d6add2187db        3 minutes ago       /bin/sh -c #(nop)  USER node                    0B
57928a6756c6        3 minutes ago       /bin/sh -c #(nop) COPY --chown=node:nodedir:…   8.8kB
ef7d474eab14        9 days ago          /bin/sh -c #(nop)  CMD ["node"]                 0B
<missing>           9 days ago          /bin/sh -c #(nop)  ENTRYPOINT ["docker-entry…   0B
<missing>           9 days ago          /bin/sh -c #(nop) COPY file:238737301d473041…   116B
<missing>           9 days ago          /bin/sh -c apk add --no-cache --virtual .bui…   5.5MB
<missing>           9 days ago          /bin/sh -c #(nop)  ENV YARN_VERSION=1.17.3      0B
<missing>           9 days ago          /bin/sh -c addgroup -g 1000 node     && addu…   69.3MB
<missing>           9 days ago          /bin/sh -c #(nop)  ENV NODE_VERSION=12.10.0     0B
<missing>           4 months ago        /bin/sh -c #(nop)  CMD ["/bin/sh"]              0B
<missing>           4 months ago        /bin/sh -c #(nop) ADD file:a86aea1f3a7d68f6a…   5.53MB
```

## Frontend

### Before

```
➜  frontend git:(master) docker history frontend
IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
8fa7998bdd6c        9 minutes ago       /bin/sh -c #(nop)  CMD ["/bin/sh" "-c" "npm …   0B
a518302798e3        9 minutes ago       /bin/sh -c #(nop)  EXPOSE 5000                  0B
f23aa4f2e5f6        9 minutes ago       /bin/sh -c #(nop)  USER app                     0B
d13f902f88b6        9 minutes ago       /bin/sh -c apt-get update &&   apt-get insta…   319MB
1ae1b6b94d35        11 minutes ago      /bin/sh -c #(nop) WORKDIR /usr/app              0B
208962d589bd        11 minutes ago      /bin/sh -c #(nop) COPY dir:5592d2203354b5427…   31.7kB
5e13f8dd4c1a        7 weeks ago         /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>           7 weeks ago         /bin/sh -c mkdir -p /run/systemd && echo 'do…   7B
<missing>           7 weeks ago         /bin/sh -c set -xe   && echo '#!/bin/sh' > /…   745B
<missing>           7 weeks ago         /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>           7 weeks ago         /bin/sh -c #(nop) ADD file:603693e48cdc7f0c5…   120MB
```

### After

```
➜  backend git:(master) ✗ docker history frontend:alpine
IMAGE               CREATED             CREATED BY                                      SIZE                COMMENT
762917142e6e        2 minutes ago       /bin/sh -c #(nop)  CMD ["npm" "start"]          0B
d3a869d5b2d1        2 minutes ago       /bin/sh -c #(nop)  EXPOSE 8000                  0B
d7121a449500        2 minutes ago       /bin/sh -c npm install                          71.5MB
c3e6ca380175        2 minutes ago       /bin/sh -c #(nop) WORKDIR /usr/app              0B
0d6add2187db        2 minutes ago       /bin/sh -c #(nop)  USER node                    0B
57928a6756c6        2 minutes ago       /bin/sh -c #(nop) COPY --chown=node:nodedir:…   8.8kB
ef7d474eab14        9 days ago          /bin/sh -c #(nop)  CMD ["node"]                 0B
<missing>           9 days ago          /bin/sh -c #(nop)  ENTRYPOINT ["docker-entry…   0B
<missing>           9 days ago          /bin/sh -c #(nop) COPY file:238737301d473041…   116B
<missing>           9 days ago          /bin/sh -c apk add --no-cache --virtual .bui…   5.5MB
<missing>           9 days ago          /bin/sh -c #(nop)  ENV YARN_VERSION=1.17.3      0B
<missing>           9 days ago          /bin/sh -c addgroup -g 1000 node     && addu…   69.3MB
<missing>           9 days ago          /bin/sh -c #(nop)  ENV NODE_VERSION=12.10.0     0B
<missing>           4 months ago        /bin/sh -c #(nop)  CMD ["/bin/sh"]              0B
<missing>           4 months ago        /bin/sh -c #(nop) ADD file:a86aea1f3a7d68f6a…   5.53MB
```
