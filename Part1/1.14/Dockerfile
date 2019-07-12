FROM ruby:2.6

EXPOSE 3000

COPY . /usr/app
WORKDIR /usr/app

RUN apt-get update && apt-get install -y nodejs

ENV SECRET_KEY_BASE = lollero

RUN bundle install
RUN rails db:migrate RAILS_ENV=production
RUN rake assets:precompile

CMD rails s -e production