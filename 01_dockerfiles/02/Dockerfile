FROM ruby:2.5

RUN apt-get update -qq
RUN apt-get install -y build-essential
RUN apt-get install -y nodejs
RUN apt-get install -y apt-utils

RUN gem install rails
RUN gem install rake

RUN mkdir /opt/app/

WORKDIR /opt/app/

RUN printf "source 'https://rubygems.org'\ngem 'rails', '5.0.0.1'" >> Gemfile
RUN touch Gemfile.lock

RUN gem install bundler && bundle install

ONBUILD RUN if [ -f rakefile ]; \
    then rake db:migrate && rake db:seed; \
    fi
