FROM ruby:2.6.3

RUN apt update
RUN apt install -y vim curl

RUN gem install rails -v 6.0.2.2

ENV NVM_DIR /root/.nvm
ENV NODE_VERSION 13.10.1

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.35.3/install.sh | bash \
    && . $NVM_DIR/nvm.sh \
    && nvm install ${NODE_VERSION}

RUN mkdir /app
WORKDIR /app

ADD Gemfile /app/Gemfile
ADD Gemfile.lock /app/Gemfile.lock

RUN bundle

ADD . /app