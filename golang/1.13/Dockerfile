FROM circleci/golang:1.13

RUN set -ex && \
    sudo apt-get update && \
    sudo apt-get install postgresql-client netcat make python python-pip python-setuptools librdkafka-dev -y --no-install-recommends && \
    pip install wheel && \
    pip install awscli

ENV PATH /home/circleci/.local/bin:$PATH
