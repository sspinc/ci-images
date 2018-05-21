FROM openjdk:8

ARG MAVEN_VERSION=3.5.3
ARG GO_VERSION=1.10.2
ARG DOCKER_VERSION=17.12.0-ce
ARG PROTOC_VERSION=3.3.0
ARG DEP_VERSION=v0.4.1

RUN mkdir /usr/local/maven \
        && curl -sSL https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz \
        | tar -xzC /usr/local/maven --strip-components 1 \
        && curl -sSL https://dl.google.com/go/go${GO_VERSION}.linux-amd64.tar.gz | tar -xzC /usr/local \
        && curl -sSL https://download.docker.com/linux/static/stable/x86_64/docker-${DOCKER_VERSION}.tgz | tar -xzC /usr/local/bin --strip-components 1 \
        && curl -sSL https://github.com/google/protobuf/releases/download/v${PROTOC_VERSION}/protoc-${PROTOC_VERSION}-linux-x86_64.zip -o /tmp/protoc.zip \
        && unzip -d /usr/local /tmp/protoc.zip \
        && rm -f /tmp/protoc.zip \
        && apt-get update \
        && apt-get install make python python-pip python-setuptools -y --no-install-recommends \
        && rm -rf /var/lib/apt/lists/* \
        && pip install wheel \
        && pip install awscli \
        && curl -sSLo /usr/local/bin/dep https://github.com/golang/dep/releases/download/${DEP_VERSION}/dep-linux-amd64 \
        && chmod +x /usr/local/bin/dep \
        && mkdir /code

ENV MAVEN_HOME /usr/local/maven
ENV PATH "$PATH:/usr/local/maven/bin:/usr/local/go/bin:/code/bin"
ENV GOPATH "/code"

RUN go get -v github.com/golang/protobuf/proto \
        && go get -v github.com/golang/protobuf/protoc-gen-go \
        && go get -v github.com/grpc-ecosystem/grpc-gateway/protoc-gen-grpc-gateway
