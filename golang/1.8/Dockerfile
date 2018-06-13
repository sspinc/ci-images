FROM golang:1.8

ARG DOCKER_VERSION=17.12.0-ce
ARG DEP_VERSION=v0.4.1
ARG PROTOC_VERSION=3.3.0

RUN curl -o /tmp/docker-${DOCKER_VERSION}.tgz https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz && \
    tar -xz -C /tmp -f /tmp/docker-${DOCKER_VERSION}.tgz && \
    mv /tmp/docker/* /usr/local/bin && \
    rm -f /tmp/docker-${DOCKER_VERSION}.tgz && \
    apt-get update && \
    apt-get install unzip postgresql-client netcat make python python-pip python-setuptools -y --no-install-recommends && \
    rm -rf /var/lib/apt/lists/* && \
    curl -Lo /tmp/protoc.zip https://github.com/google/protobuf/releases/download/v${PROTOC_VERSION}/protoc-${PROTOC_VERSION}-linux-x86_64.zip && \
    unzip -d /usr/local /tmp/protoc.zip && \
    rm -f /tmp/protoc.zip && \
    pip install wheel && \
    pip install awscli && \
    go get -v github.com/golang/protobuf/proto && \
    go get -v github.com/golang/protobuf/protoc-gen-go && \
    go get -v github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway && \
    curl -Lo /usr/local/bin/dep https://github.com/golang/dep/releases/download/${DEP_VERSION}/dep-linux-amd64 && \
    chmod +x /usr/local/bin/dep
