FROM ruby:2.5

RUN apt-get update
RUN apt-get install -y build-essential
RUN apt-get install -y nodejs
RUN gem install rails

RUN mkdir -p /app
WORKDIR /app

COPY Gemfile Gemfile.lock ./
RUN gem install bundler && bundle install

RUN mkdir -p /opt/app
COPY * /opt/app

ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
