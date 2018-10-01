FROM python:3.7

ARG DOCKER_VERSION=17.12.0-ce

RUN apt-get update \
        && apt-get install netcat postgresql-client unzip -y --no-install-recommends \
        && rm -rf /var/lib/apt/lists/* \
        && curl -sSL https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz | tar -xzC /usr/local/bin --strip-components 1 \
        && pip install awscli virtualenv
