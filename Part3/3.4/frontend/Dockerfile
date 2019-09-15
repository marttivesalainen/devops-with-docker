FROM node:alpine

COPY --chown=node:node . /usr/app

USER node

WORKDIR /usr/app

RUN npm install

EXPOSE 5000

CMD ["npm", "start"]