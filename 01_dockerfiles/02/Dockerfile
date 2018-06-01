FROM ruby:2.5

RUN apt-get update -qq
RUN apt-get install -y build-essential
RUN apt-get install -y nodejs
RUN apt-get install -y apt-utils

RUN gem install rails
RUN gem install rake

RUN mkdir /opt/app/
WORKDIR /opt/app/

COPY Gemfile /app/Gemfile
COPY Gemfile.lock /app/Gemfile.lock

RUN gem install bundler && bundle install

COPY app/ /opt/app/

ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:seed
