FROM ubuntu:16.04

COPY . /usr/app
WORKDIR /usr/app

RUN apt-get update && \
  apt-get install -y curl && \
  curl -sL https://deb.nodesource.com/setup_10.x | bash && \
  apt-get install -y nodejs && \
  npm install && \ 
  apt-get purge -y --auto-remove curl && \ 
  rm -rf /var/lib/apt/lists/* && \
  useradd -m app && \
  chown -R app:app /usr/app

USER app

EXPOSE 5000

CMD npm start