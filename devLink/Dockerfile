FROM ruby:1.9.3
MAINTAINER thrively

RUN apt-get update -qq && apt-get install -y \

build-essential \
#Memcached
memcached

RUN mkdir /app && \
    cd /app

COPY . /app

VOLUME /app

WORKDIR /app

RUN bundle install

EXPOSE 3000

CMD service memcached start && \
    bundle exec puma -C config/puma.rb
