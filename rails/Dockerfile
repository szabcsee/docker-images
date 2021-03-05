ARG RUBY_VERSION
ARG YARN_VERSION

#Ruby & Bundler & postgresql-client
FROM ruby:$RUBY_VERSION

ENV ROOT=/app \
  LANG=en_GB.UTF-8 \
  TZ=Europe/Budapest

WORKDIR ${ROOT}

RUN apk add --update nodejs nodejs-npm

    # fix npm - not the latest version installed by apt-get
RUN npm install -g npm

RUN apk add --no-cache yarn

# Packages
RUN apk update && \
  apk upgrade && \
  apk add --no-cache \
  gcc \
  g++ \
  libc-dev \
  libxml2-dev \
  linux-headers \
  make \
  postgresql \
  postgresql-dev \
  tzdata \
  less \
  git && \
  apk add --virtual build-packs --no-cache \
  build-base \
  curl-dev

COPY Gemfile ${ROOT}
COPY Gemfile.lock ${ROOT}

RUN bundle install -j4 && \
  apk del build-packs

COPY . ${ROOT}

RUN node -v \
    npm -v \
    yarn -v
