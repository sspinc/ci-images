FROM circleci/golang:1.11

RUN set -ex && \
    sudo apt-get update && \
    sudo apt-get install postgresql-client netcat make python python-pip python-setuptools -y --no-install-recommends && \
    pip install wheel && \
    pip install awscli

ENV PATH /home/circleci/.local/bin:$PATH
