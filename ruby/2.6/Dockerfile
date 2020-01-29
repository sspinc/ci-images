FROM circleci/ruby:2.6-node

RUN curl -sL https://bitbucket.org/ariya/phantomjs/downloads/phantomjs-2.1.1-linux-x86_64.tar.bz2 \
    | sudo tar -xj -C /usr/local/bin -f- --strip-components 2 phantomjs-2.1.1-linux-x86_64/bin/phantomjs \
    && sudo apt-get update \
    && sudo apt-get install --no-install-recommends -y postgresql-client \
    && sudo rm -rf /var/lib/apt/lists/*
