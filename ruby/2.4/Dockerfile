FROM circleci/ruby:2.4-node

RUN curl -sL https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2 \
    | tar -xj -C /usr/local/bin -f- --strip-components 2 phantomjs-2.1.1-linux-x86_64/bin/phantomjs \
    && apt-get update \
    && apt-get install --no-install-recommends -y postgresql-client \
    && rm -rf /var/lib/apt/lists/*
