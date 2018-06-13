FROM ruby
MAINTAINER vlevko@student.unit.ua

RUN apt-get update -y
RUN apt-get install build-essential -y
RUN apt-get install nodejs -y

RUN gem install rails

RUN mkdir -p /opt/app

EXPOSE 3000
WORKDIR /opt/app

ONBUILD COPY myapp/ /opt/app
ONBUILD RUN gem install bundler
ONBUILD RUN bundle install
ONBUILD RUN rake db:migrate
ONBUILD RUN rake db:setup
ONBUILD RUN rake db:seed
