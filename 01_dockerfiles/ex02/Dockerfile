FROM ruby:2.5

RUN apt-get update -y
RUN apt-get upgrade -y
RUN apt-get install nodejs -y
RUN gem install rails
ONBUILD COPY . /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD RUN bundle install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed
