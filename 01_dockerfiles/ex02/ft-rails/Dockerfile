FROM ruby

RUN     apt-get update -qq && apt-get install -y build-essential
ONBUILD RUN mkdir /opt/app
ONBUILD WORKDIR /opt/app
ONBUILD ADD ../app/ .
ONBUILD WORKDIR /opt/app/
ONBUILD RUN bundle install
