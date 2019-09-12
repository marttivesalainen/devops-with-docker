# 3.1

## Backend

### First iteration

```
IMAGE               CREATED              CREATED BY                                      SIZE                COMMENT
9e8e486b23d7        18 seconds ago       /bin/sh -c #(nop)  CMD ["/bin/sh" "-c" "npm …   0B
f88ae86b6bda        18 seconds ago       /bin/sh -c #(nop)  EXPOSE 8000                  0B
7112fac84add        19 seconds ago       /bin/sh -c npm install                          71.5MB
3015af7d2a97        42 seconds ago       /bin/sh -c apt-get install -y nodejs            98.2MB
d87f8d5a5661        53 seconds ago       /bin/sh -c curl -sL https://deb.nodesource.c…   33.6MB
1cbecc0b0067        About a minute ago   /bin/sh -c apt-get install -y curl              16.3MB
74be5c5451b0        About a minute ago   /bin/sh -c apt-get update                       25.4MB
667eba302d01        About a minute ago   /bin/sh -c #(nop) WORKDIR /usr/app              0B
34716a851da1        About a minute ago   /bin/sh -c #(nop) COPY dir:84072922dc0d60251…   8.9kB
5e13f8dd4c1a        7 weeks ago          /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>           7 weeks ago          /bin/sh -c mkdir -p /run/systemd && echo 'do…   7B
<missing>           7 weeks ago          /bin/sh -c set -xe   && echo '#!/bin/sh' > /…   745B
<missing>           7 weeks ago          /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>           7 weeks ago          /bin/sh -c #(nop) ADD file:603693e48cdc7f0c5…   120MB
```

### After improvements

```
IMAGE               CREATED              CREATED BY                                      SIZE                COMMENT
20654bc122d7        59 seconds ago       /bin/sh -c #(nop)  CMD ["/bin/sh" "-c" "npm …   0B
b675050d8362        59 seconds ago       /bin/sh -c #(nop)  EXPOSE 8000                  0B
df690e116c00        About a minute ago   /bin/sh -c apt-get update &&   apt-get insta…   217MB
055bd94767d6        2 minutes ago        /bin/sh -c #(nop) WORKDIR /usr/app              0B
791bd3ed5021        2 minutes ago        /bin/sh -c #(nop) COPY dir:0d63fa642c2e5008e…   8.99kB
5e13f8dd4c1a        7 weeks ago          /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>           7 weeks ago          /bin/sh -c mkdir -p /run/systemd && echo 'do…   7B
<missing>           7 weeks ago          /bin/sh -c set -xe   && echo '#!/bin/sh' > /…   745B
<missing>           7 weeks ago          /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>           7 weeks ago          /bin/sh -c #(nop) ADD file:603693e48cdc7f0c5…   120MB
```

## Frontend

### First iteration

```
IMAGE               CREATED              CREATED BY                                      SIZE                COMMENT
2812d0ef3bb7        About a minute ago   /bin/sh -c #(nop)  CMD ["/bin/sh" "-c" "npm …   0B
25ee5282237d        About a minute ago   /bin/sh -c #(nop)  EXPOSE 5000                  0B
cd17e81b719d        About a minute ago   /bin/sh -c npm install                          174MB
ba39a560fbc5        About a minute ago   /bin/sh -c apt-get install -y nodejs            98.2MB
5bd925aaebf9        2 minutes ago        /bin/sh -c curl -sL https://deb.nodesource.c…   33.6MB
50f8f4f7ff7d        2 minutes ago        /bin/sh -c apt-get install -y curl              16.3MB
d0088f51c0b4        2 minutes ago        /bin/sh -c apt-get update                       25.4MB
145a255731b0        2 minutes ago        /bin/sh -c #(nop) WORKDIR /usr/app              0B
c7ad7de8fbd5        2 minutes ago        /bin/sh -c #(nop) COPY dir:27e5f7e3d6a539696…   31.5kB
5e13f8dd4c1a        7 weeks ago          /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>           7 weeks ago          /bin/sh -c mkdir -p /run/systemd && echo 'do…   7B
<missing>           7 weeks ago          /bin/sh -c set -xe   && echo '#!/bin/sh' > /…   745B
<missing>           7 weeks ago          /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>           7 weeks ago          /bin/sh -c #(nop) ADD file:603693e48cdc7f0c5…   120MB
```

### After improvements

```
IMAGE               CREATED              CREATED BY                                      SIZE                COMMENT
d4b8b2845aa6        6 seconds ago        /bin/sh -c #(nop)  CMD ["/bin/sh" "-c" "npm …   0B
0c4926ed6553        6 seconds ago        /bin/sh -c #(nop)  EXPOSE 5000                  0B
fb615bf00178        8 seconds ago        /bin/sh -c apt-get update &&   apt-get insta…   319MB
ff866fcf299f        About a minute ago   /bin/sh -c #(nop) WORKDIR /usr/app              0B
8fdc3a818ac4        About a minute ago   /bin/sh -c #(nop) COPY dir:99cdbc09356662357…   31.6kB
5e13f8dd4c1a        7 weeks ago          /bin/sh -c #(nop)  CMD ["/bin/bash"]            0B
<missing>           7 weeks ago          /bin/sh -c mkdir -p /run/systemd && echo 'do…   7B
<missing>           7 weeks ago          /bin/sh -c set -xe   && echo '#!/bin/sh' > /…   745B
<missing>           7 weeks ago          /bin/sh -c rm -rf /var/lib/apt/lists/*          0B
<missing>           7 weeks ago          /bin/sh -c #(nop) ADD file:603693e48cdc7f0c5…   120MB
```
