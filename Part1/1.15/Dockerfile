FROM node:latest

WORKDIR /usr/app

EXPOSE 3000
ENV PORT 3000

RUN git clone https://github.com/marttivesalainen/node-hello-world.git . && npm install

CMD ["node", "/usr/app/index.js"]